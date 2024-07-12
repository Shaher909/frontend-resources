# Next.JS

Next.js is React framework that is built on top of React. It provides quick setup with 0 configuration possiblities, and supports SEO and rapid development.
Official site: https://nextjs.org/

**React Client Site Rendering (CSR):**
server sends response to browser -> browser downloads JS -> Browser execute -> page is visible and ineractive. In this case users could see a blank page until the execution takes place.

**Next.js Server Side Rendering (SSR):**
server response with ready to be rendered HTML to browser -> browser renders HTML and page is visible -> Browser downloads JS and execute React -> (Hydration) JS is downloaded and page is interactive


## Features:
- Built in routing service: each time a file is added into the _pages_ directory, a new route with the name would be available.


## Getting Started:
- Create APP (CLI), steps:
#1
`npm create next-app`
or
`yarn create next-app`

#2 `npx create-next-app _app-name_`

#3 `npm run dev` 


## File Structure:
- **package.json** file contains the manifest of the project with references to all dependencies & metadata of the APP
- **node_modules** directly: contains all the dependencies
- **pages** directory: contains the pages and views of the application
-- **api** directory: contains the calls with the server (specifically)
- **styles** directory: contains the CSS
