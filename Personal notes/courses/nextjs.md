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
- (depricated) **pages** directory: contains the pages and views of the application 
- **app** directory: contains the routes structure of the APP 
-- **api** directory: contains the calls with the server (specifically)
- **styles** directory: contains the CSS

## Project file structure:
<!-- Below is not the latest concepts, as NextJS have a new concept of "app" which replaces pages-->
Pages --> _app.js : represents the entry point to the APP (starting point). 
Pages --> api: this is a directory to setup routes that only apply to the server. (this will not be included into the bundle send to the client side).

## Documentation
To get NextJS installed and to review other specifications, visit: https://nextjs.org/docs

# Inner workings of NextJS
- In NextJS a page is nothing but a react component.
- When creating a new component, the name of the .js file will define the route to this component.
It's important to use: 
`export default componentName`
in order to export the component from the JS file.

- .next directly --> contains the outcome of the "build" that your run on your porject and will be published for actual use.

- React offers various options to create components:
#1 Server components (rendered & optionally cached on the server) -> used by default
If there's a need to specify explicitly that something needs to run on the server, then 'use server' is used (this could happen within another component that renders other parts on the client side).
#2 Client components (pre-rendered on the server) and uses client JS to run in browser -> to use it, specify 'use client' on top of the component JS file.

What's hydration? It's the process of attaching event listeners to the DOM to make static HTML interactive.

## Routing:
- Using React Router and client side routing via the link component.
In the older versions of nextJS, the Pages directory automatically creates routes within the 'pages' folder. While in the newer versions from 2023 onwards, the App Router organizes routes within the 'app' folder.

To create a route: create a folder within 'app' and create the "page" component (.js, .tsx ..etc.) inside of it. It's critical that the name of the file is page.js inside each folder.
The folder name would represent the URL path.
The `Link` component is used to navigate from one route to the other.

### Dynamic Routes:
For large applications, it's often the case, that the URL path would contain dynamic part, ex: /category/productCode (in this case productCode is dynamic).

Using APP router, Dynamic Segments are used and gets filled during request time (or at build time).
To use it, name the folder using [].
Then inside the folder, create the page.tsx file, and then inside it you can capture the value from the URL path (ex: passed during the request) to react on it and load the necessary content accordingly:
`
export default function Page({ params }: { params: { id: string } }) {
  return <div>My Post: {params.id}</div>
}
`

http://localhost:3000/product/id which corresponds to the file structure > src/app/product/[id]/page.tsx


# Quick recap
- When using newer versions of Next.JS - the app starts from the 'app' folder -> page.tsx.
- Defining new directories is possible by creating folders and create page.tsx in each of them.
- the '.next' folder provides the built version of the application.
- when using console.log() by default this will not be visible in the browser (as it rendered on the server side), to make it in the browser use úse client´ at the top of the component (this makes it render on client side).