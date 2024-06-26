# Performance Metrics
**Page Weight:** an important factor that affect load time and the cost of loading the webpage for customers using mobile devices. In order to reduce the weight, there're key areas to look at:
- Images make up more than 50% of website's page weight, so consider reducing the quality of some images.
- Use latest markup to render images, ex: responsbile image <picture> tag and srcset attribute to download appropriately sized images
- Too many custom fonts will increase the page weight.
- JS and CSS frameworks add a lot of weight so consider moving away from some libraries even if it means doing something on your own, or sacrificing the support for some older browser versions if you can offer some sort of fallback. Take advantage of minification and compression tools.

# Useful tools
1- HTTPArchive: https://httparchive.org/reports is a useful tool that provides average baseline for many important performance metrics.
2- What does my site cost? https://whatdoesmysitecost.com is a useful tool that calcaulates the cost of a webpage loading in different countries.