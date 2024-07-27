- Disable automatic updates for 3rd party frameworks and libraries, but ensure there are processes to update them frequently.
- Leverage NPM lock files to keep versions in sync across envs.
- Ask your API team to provide obscure error responses (don't provide preceise error messages to the front-end)
- Run automatic audit on your application frequently using commands like: 
`npm audit`
and find other tools that can support as well (Snyk, Sonatype ..etc.)
- Validate user's input well, and anticipate edge cases (file format, length and type of content)
- Scan uploaded content for Trojan horses (uploaded files could contain dangerous JS content for example)
- Explore content-security-policy on meta tags and HTTP headers:
-- Connect-src: to limit the locations where your page can connect via XHR, Websockets and EventSource
-- Form-action: to limit the locations to which your forms can be submitted
-- Style-src and script-src: to limit the locations from which page can load CSS and JS
- Watch out for the browser plugins the developers use (as they have very high privilage usually)
- Avoid using user's specific data in URL parameter
-