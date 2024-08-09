Next.js is a free and open source react-based framework which supports static and server-rendered pages which help to build dynamic and hybrid applications. While stand-alone react app are client-side rendered.
It builds on top of React.js to provide additional services, features and tools (bundling, compiling, fetching data, routing and TypeScript ..etc.)
NextJS is ideal for eCommerce, marketing and portfolio sites when changes are done in real-time.. it's a front-end tool set.


# Features:
- Data Fetching: next.js allows us to fetch data and render HTML on the server which allow quicker loading time & bots to crawl this content.

It can run:
#1 Server-side rendering which entails dynamic generation where the server renders the React application generating the HTML
#2 Static site generation in which it pre-renders the site by copying files (which iclude rendered routes) into CDN which increases the speed of the site. This is good in use cases in which content does not change that often.
#3 Static incremental rendering in which statid and dynamic properties are comgined allowing generation of static content but at the time providing possiblity to updaing certain elements before the generation.
#4 Client side rendering which is good pages with heavy data load (CSR) (not optimal for SEO)

It supports:
#1 Using TypeScript
#2 File-based router supporting layouts, nested routing and error handling
#3 Styling via CSS modules, tailwind or CSS-in-JS
#4 Data Fetching through async/await in server components.
#5 Optimizations for images, fonts and scripts.

# Setup:
NextJS comes with a default setup that allows a quick start, with directories for specific purposes and automatic routing.

## Routing:
- Using React Router and client side routing via the link component.
In the older versions of nextJS, the Pages directory automatically creates routes within the 'pages' folder. While in the newer versions from 2023 onwards, the App Router organizes routes within the 'app' folder.

To create a route: create a folder within 'app' and create the "page" component (.js, .tsx ..etc.) inside of it. It's critical that the name of the file is page.js inside each folder.
The folder name would represent the URL path.
The `Link`component is used to navigate from one route to the other.

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


# Quick recap
- When using newer versions of Next.JS - the app starts from the 'app' folder -> page.tsx.
- Defining new directories is possible by creating folders and create page.tsx in each of them.
- the '.next' folder provides the built version of the application.
