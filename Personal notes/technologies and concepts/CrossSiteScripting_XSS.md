# Cross Site Scripting - XSS
In Crosssite scripting a malicious code is injected into the web page with intent of reading data or performing operations on behalf of the user.
Usually this happens via submitting the code in a form field or via URL parameter.

It's often the case that we rely on our back-end systems to validate against such entries, but the issue is, is that often we use such input on the front-end even before the data is sent to the back-end to render content on the page, ex: Welcome $username .. or in form validation when showing error messages ..etc.

Some techniques to minmize the risk of XSS on the front-end:
- Try to overwrite the JS' "eval" method to make it unusable in the application
- Force disable the unsafe interpolations on your libraries
- Create sha-256 integrity keys for your scripts (to reduce XSS through man-in-the-middle attacks)
- Watch out for texts HTML embedded inside image files (some images can contain unwanted instructions that run in the browser)


