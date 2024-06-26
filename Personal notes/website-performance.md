# Performance Metrics
**Page Weight:** an important factor that affect load time and the cost of loading the webpage for customers using mobile devices. In order to reduce the weight, there're key areas to look at:
- Images make up more than 50% of website's page weight, so consider reducing the quality of some images.
- Use latest markup to render images, ex: responsbile image <picture> tag and srcset attribute to download appropriately sized images
- Too many custom fonts will increase the page weight.
- JS and CSS frameworks add a lot of weight so consider moving away from some libraries even if it means doing something on your own, or sacrificing the support for some older browser versions if you can offer some sort of fallback. Take advantage of minification and compression tools.

**Number of HTTP requests:** for every single resource loading on the webpage, the browser needs to create a request to fetch it. A browser has a limited amount of concurrent requests that can take place in parallel, hence having some many of them means numerous round trips to the server which could be affected by slow network, so limiting the number of requests can improve the perfomrance.
-> think about concatenatinv various css and js files into 1 file
-> combine individual images into a single image map or icon font
-> Lazy load assets that are not needed for initial page load
-> Split assets per server (ex: different CNDs) because the limits of fetching assets is per server.

**Speed Index:** the average time at which visible part of the website are displayed (it's measured in ms and depends onthe viewport).

## Timing Metrics
**Time to first byte (TTFB):** the number of ms between the browser request to the page, and the first byte being received by the browser (including DNS lookup and network connection).

**Time to start render:** This is time taken for the user to see any content on the page. Which basically means the browser is able to start rendering the DOM. Keep an eye on any blocking JS/CSS on your web page or lazy load them later after the document render, think about rendering inline CSS (crucial ones).

**Time to document complete:** the time needed to load all of the initially requested assets.

# Useful tools
1- HTTPArchive: https://httparchive.org/reports is a useful tool that provides average baseline for many important performance metrics.

2- What does my site cost? https://whatdoesmysitecost.com is a useful tool that calcaulates the cost of a webpage loading in different countries.

3- PageSpeed: https://pagespeed.web.dev analyzes the perofmance and usability of a website.

4- Grunt PageSpeed: https://www.npmjs.com/package/grunt-pagespeed - plugins that allow automating the workflow of testing a webpage which can be added as a test in a project to test against a specific budget (value that should be passed).

5- Grunt Perfbudget: https://github.com/tkadlec/grunt-perfbudget - plugins into WebPageTest API