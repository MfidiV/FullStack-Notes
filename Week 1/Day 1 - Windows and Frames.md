# FRAMES AND WINDOWS
### POPUPS
Popups exist from really ancient times. The initial idea was to show another content without closing the main window. As of now, there are other ways to do that: we can load content dynamically with fetch and show it in a dynamically generated. So, popups are not something we use every day.

A popup is a new browser window that appears on top of the current browser window. It can be used to display additional content, alerts, prompts, or other UI elements.

<b>Still, there are tasks where popups are still used, e.g. for OAuth authorization (login with Google/Facebook/…), because:</b>

+ A popup is a separate window with its own independent JavaScript environment. So, opening a popup with a third-party non-trusted site is safe.
+ It’s very easy to open a popup.
+ A popup can navigate (change URL) and send messages to the opener window.

### Window.Open
+ The syntax to open a popup is: window.open(url, name, params)
+ An URL to load into the new window.

+ •	A name of the new window. Each window has a window.name, and here we can specify which window to use for the popup. If there’s already a window with such name – the given URL opens in it, otherwise a new window is opened. 

+  	Params - The configuration string for the new window. It contains settings, delimited by a comma. There must be no spaces in params, for instance: width:200,height=100.
+ Setting for params:
+ + menubar (yes/no) – shows or hides the browser menu on the new window.

+ + toolbar (yes/no) – shows or hides the browser navigation bar (back, forward, reload etc) on the new window.
+ + location (yes/no) – shows or hides the URL field in the new window. FF and IE don’t allow to hide it by default.

+ + status (yes/no) – shows or hides the status bar. Again, most browsers force it to show.
+ + resizable (yes/no) – allows to disable the resize for the new window. Not recommended.
+ + There is also a number of less supported browser-specific features, which are usually not used


## Minimalistic window
Rules for omitted settings:

+ If there is no 3rd argument in the open call, or it is empty, then the default window parameters are used.

+ If there is a string of params, but some yes/no features are omitted, then the omitted features assumed to have no value. So if you specify params, make sure you explicitly set all required features to yes

+	If there is no left/top in params, then the browser tries to open a new window near the last opened window.

+ If there is no width/height, then the new window will be the same size as the last opened.

### Accessing popup from window

let newWin = window.open("about:blank", "hello", "width=200,height=200");
newWin.document.write("Hello, world!");

### Accessing window from popup
    
 

### Windows pop up
+ To close a window: win.close().
+ To check if a window is closed: win.closed.
+ Technically, the close() method is available for any window, but window.close() is ignored by most browsers if window is not created with window.open(). So it’ll only work on a popup.
 # SCROLLING A WINDOW

+ <span>win.scrollBy(x,y)</span>
Scroll the window x pixels right and y down relative the current scroll. Negative values are allowed.
+ win.scrollTo(x,y)
Scroll the window to the given coordinates (x,y).
+ elem.scrollIntoView(top = true)
Scroll the window to make elem show up at the top (the default) or at the bottom for elem.scrollIntoView(false).
<b>NB:There’s also window.onscroll event.</b>


