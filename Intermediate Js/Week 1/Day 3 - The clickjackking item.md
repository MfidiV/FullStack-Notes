The clickjacking attack

The “clickjacking” attack allows an evil page to click on a “victim site” on behalf of the visitor.
Many sites were hacked this way, including Twitter, Facebook, Paypal and other sites. They have all been fixed, of course.
The idea
The idea is very simple.
Here’s how clickjacking was done with Facebook:
1.	A visitor is lured to the evil page. It doesn’t matter how.
2.	The page has a harmless-looking link on it (like “get rich now” or “click here, very funny”).
3.	Over that link the evil page positions a transparent <iframe> with src from facebook.com, in such a way that the “Like” button is right above that link. Usually that’s done with z-index.
4.	In attempting to click the link, the visitor in fact clicks the button.

Clickjacking is for clicks, not for keyboard
The attack only affects mouse actions (or similar, like taps on mobile).
Keyboard input is much difficult to redirect. Technically, if we have a text field to hack, then we can position an iframe in such a way that text fields overlap each other. So when a visitor tries to focus on the input they see on the page, they actually focus on the input inside the iframe.
But then there’s a problem. Everything that the visitor types will be hidden, because the iframe is not visible.
People will usually stop typing when they can’t see their new characters printing on the screen.
Old-school defences (weak)
The oldest defence is a bit of JavaScript which forbids opening the page in a frame (so-called “framebusting”).
That looks like this:
if (top != window) {
  top.location = window.location;
}
That is: if the window finds out that it’s not on top, then it automatically makes itself the top.
This not a reliable defence, because there are many ways to hack around it. Let’s cover a few.
Blocking top-navigation
We can block the transition caused by changing top.location in beforeunload event handler.
The top page (enclosing one, belonging to the hacker) sets a preventing handler to it, like this:
window.onbeforeunload = function() {
  return false;
};
When the iframe tries to change top.location, the visitor gets a message asking them whether they want to leave.
In most cases the visitor would answer negatively because they don’t know about the iframe – all they can see is the top page, there’s no reason to leave. So top.location won’t change!
In action:
Result
iframe.html
index.html
Sandbox attribute
One of the things restricted by the sandbox attribute is navigation. A sandboxed iframe may not change top.location.
So we can add the iframe with sandbox="allow-scripts allow-forms". That would relax the restrictions, permitting scripts and forms. But we omit allow-top-navigation so that changing top.location is forbidden.
Here’s the code:
<iframe sandbox="allow-scripts allow-forms" src="facebook.html"></iframe>
There are other ways to work around that simple protection too.
X-Frame-Options
The server-side header X-Frame-Options can permit or forbid displaying the page inside a frame.
It must be sent exactly as HTTP-header: the browser will ignore it if found in HTML <meta> tag. So, <meta http-equiv="X-Frame-Options"...> won’t do anything.
The header may have 3 values:
DENY
Never ever show the page inside a frame.
SAMEORIGIN
Allow inside a frame if the parent document comes from the same origin.
ALLOW-FROM domain
Allow inside a frame if the parent document is from the given domain.
For instance, Twitter uses X-Frame-Options: SAMEORIGIN.
Here’s the result:
<iframe src="https://twitter.com"></iframe>
Depending on your browser, the iframe above is either empty or alerting you that the browser won’t permit that page to be navigating in this way.
Showing with disabled functionality
The X-Frame-Options header has a side effect. Other sites won’t be able to show our page in a frame, even if they have good reasons to do so.
So there are other solutions… For instance, we can “cover” the page with a <div> with styles height: 100%; width: 100%;, so that it will intercept all clicks. That <div> is to be removed if window == top or if we figure out that we don’t need the protection.

