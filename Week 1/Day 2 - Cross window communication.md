# Cross window communication

## Same origin
+ The “Same Origin” policy states that;
+ + if we have a reference to another window, e.g. a popup created by window.open or a window inside , and that window comes from the same origin, then we have full access to that window.
otherwise, if it comes from another origin, then we can’t access the content of that window: variables, document, anything. The only exception is location: we can change it (thus redirecting the user). But we cannot read the location (so we can’t see where the user is now, no information leak).

## In action-iFrame

+ An iframe tag hosts a separate embedded window, with its own separate document and window objects.
+ We can access them using properties:
+ + iframe.contentWindow to get the window inside the .
+ + iframe.contentDocument to get the document inside the iframe, короткий аналог iframe.contentWindow.document

When we access something inside the embedded window, the browser checks if the iframe has the same origin. If that’s not so then the access is denied (writing to location is an exception, it’s still permitted).

<b>iframe.onload vsiframe.contentWindow.onload</b>

The iframe.onload event (on the iframetag) is essentially the same as iframe.contentWindow.onload (on the embedded window object). It triggers when the embedded window fully loads with all resources.
…But we can’t access iframe.contentWindow.onload for an iframe from another origin, so using iframe.onload.

Windows on subdomains: document.domain
By definition, two URLs with different domains have different origins.
But if windows share the same second-level domain, for instance, john.site.com, peter.site.com, and site.com (so that their common second-level domain is site.com), we can make the browser ignore that difference, so that they can be treated as coming from the “same origin” for the purposes of cross-window communication.
To make it work, each such window should run the code:
document.domain = 'site.com';
That’s all. Now they can interact without limitations. Again, that’s only possible for pages with the same second-level domain.

Iframe: wrong document pitfall
•	When an iframe comes from the same origin, and we may access its document, there’s a pitfall. It’s not related to cross-domain things, but important to know.
•	Upon its creation, an iframe immediately has a document. But that document is different from the one that loads into it!
•	So if we do something with the document immediately, that will probably be lost.

•	We shouldn’t work with the document of a not-yet-loaded iframe, because that’s the wrong document. If we set any event handlers on it, they will be ignored.
•	How to detect the moment when the document is there?
•	The right document is definitely at the place when iframe.onload triggers. But it only triggers when the whole iframe with all resources is loaded.
We can try to catch the moment earlier using checks in setInterval

The sandbox attribute
The sandbox attribute allows for the exclusion of certain actions inside an <iframe> in order to prevent it from executing untrusted code. It “sandboxes” the iframe by treating it as coming from another origin and/or applying other limitations.
There’s a “default set” of restrictions applied for <iframe sandbox src="...">. But it can be relaxed if we provide a space-separated list of restrictions that should not be applied as a value of the attribute, like this: <iframe sandbox="allow-forms allow-popups">.
In other words, an empty "sandbox" attribute puts the strictest limitations possible, but we can put a space-delimited list of those that we want to lift.
Here’s a list of limitations:
•	allow-same-origin
By default "sandbox" forces the “different origin” policy for the iframe. In other words, it makes the browser to treat the iframe as coming from another origin, even if its src points to the same site. With all implied restrictions for scripts. This option removes that feature.
•	allow-top-navigation
Allows the iframe to change parent.location.
•	allow-forms
Allows to submit forms from iframe.
•	allow-scripts
Allows to run scripts from the iframe.
•	allow-popups
Allows to window.open popups from the iframe
It demonstrates a sandboxed iframe with the default set of restrictions: <iframe sandbox src="...">. It has some JavaScript and a form.
Please note that nothing works. So the default set is really harsh.
Please note:
The purpose of the "sandbox" attribute is only to add more restrictions. It cannot remove them. In particular, it can’t relax same-origin restrictions if the iframe comes from another origin.


Cross Window Messaging
The postMessage interface allows windows to talk to each other no matter which origin they are from.

The interface has two parts.
	postMessage
The window that wants to send a message calls postMessage method of the receiving window. In other words, if we want to send the message to win, we should call win.postMessage(data, targetOrigin).
•	Data - The data to send. Can be any object, the data is cloned using the “structured cloning algorithm”. IE supports only strings, so we should JSON.stringify complex objects to support that browser.
•	TargetOrigin - Specifies the origin for the target window, so that only a window from the given origin will get the message.
The targetOrigin is a safety measure. Remember, if the target window comes from another origin, we can’t read it’s location in the sender window. So we can’t be sure which site is open in the intended window right now: the user could navigate away, and the sender window has no idea about it.
Specifying targetOrigin ensures that the window only receives the data if it’s still at the right site. Important when the data is sensitive.
	onmessage
To receive a message, the target window should have a handler on the message event. It triggers when postMessage is called (and targetOrigin check is successful).
The event object has special properties:
data
The data from postMessage.
origin
The origin of the sender, for instance http://javascript.info.
source
The reference to the sender window. We can immediately source.postMessage(...) back if we want.
To assign that handler, we should use addEventListener, a short syntax window.onmessage does not work.
