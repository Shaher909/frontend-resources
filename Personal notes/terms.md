**Component:** a visual representation of a small piece of content. They should usually be dumb and flexible, without an influence on their with, background or external margins and padding. The benefit of this would be that when using those components in a layout, let's say three-column based, they'd all line up perfectly (because no component has a top margin).

**Component modifier (skin or subcomponent):** this term could differ depending on the used methodology, but refers to the class that are assinged to allow having multiple variations of a component so it can be used in different circumstances.

**Fluid grids:** percentage based width rather than fixed-pixel dimensions

**Flexible images:** 100% width images fill the container they are put in and flex as the view port changes size

**Media queries:** Being able to specify different styles for different view port sizes, now we can change the page layout based on the size of the screen.
Div soup: when many divs are nested in on top of each other to achieve a special layout for a simple content at the center of those divs (this is comes from procedural markup)

**Task Runner:** in the context of node.js, a task runner ir a tool that automate reptitive tasks invovled in the development workflow such as: running tests or specific commands, minifying CSS or deploying code to servers, and many others.
There're multiple tasks runners like Gulp, Grunt and npm scripts (even though not a task runner per say).
Example: for npm scripts, the details are stored the package.json file:
```
{
  "scripts": {
    "watch": "npm-run-all --parallel watch:sass watch:scripts",
    "build": "npm run sass && npm run scripts",
  }
}
```
Then you can use npm build to run the task as specified above.

**Unit testing:** the process of breaking down the application code to the smallest possible functions and creating repeatable, automated tests that continually produce the same result.