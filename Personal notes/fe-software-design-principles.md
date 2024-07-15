# CSS
## 1- Single Responsibility Principle
Everything that is created for one single purpose.

A bad example, would be:
```html
<div class="calendar">
  <h2 class="primary-header">This Is a Calendar Header</h2>
</div>

<div class="blog">
  <h2 class="primary-header">This Is a Blog Header</h2>
</div>

<style>
.calendar-header {
  color: red;
  font-size: 2em;
}
</style>
```
In the preeeding code, any future change to the .primary-header will affect both elements, which reduces flexibility and can creates complications as the code grows larger.

A good example, would be:
```html
<div class="calendar">
  <h2 class="calendar-header">This Is a Calendar Header</h2>
</div>

<div class="blog">
  <h2 class="blog-header">This Is a Blog Header</h2>
</div>

<style>
.calendar-header {
  color: red;
  font-size: 2em;
}

.blog-header {
  color: red;
  font-size: 2.4em;
}
</style>
```


## 2- Single Source of Truth Principle
All styles that are applied to a class come from a single source.

Let's say we have the following code:
```html
    <div class="table">
        <h2 class="table-header">This Is a Blog Header</h2>
        ...
        <div class="calendar">
        <h2 class="calendar-header">This Is a Calendar Header</h2>
        </div>
    </div>
```

A bad example would be:
```css
/* calendar.css */
.calendar-header {
  color: red;
  font-size: 2em;
}

/* table.css */
.table-header {
  color: red;
  font-size: 2.4em;
}

.table .calendar-header {
  font-size: 1.6em;
}
```
In the preceding code, the calendar element would be styled by two different files, which makes it harder to keep an overview of the changes and their implication on this element when things get complicated in the project.

While a better code, would be:
```css
/* calendar.css */
.calendar-header {
  color: red;
  font-size: 2em;
}

.table .calendar-header {
  font-size: 1.6em;
}

/* table.css */
.table-header {
  color: red;
  font-size: 2.4em;
}
```
In the preceding code we can see that the calendar element is styled only via one file, even when targeting a specific use case based on its parent element.

## 3- Separation of concerns
Break down a computer program into different modules according to their responsibilities. And split the code according to their scope of action such as model, views and controllers.

## 4- Principle of least knowledge
Or law of Demeter (LoD) refers to the idea of each unit of a program only having knowledge about itself. In other words, each unit should loosely coupled with its surroundings. (This increases reusability).

## 5- Minimization of large design up front
Big Design Up Front (BDUF) is the waterfall model of software development, in which system design is complete before the implementation starts. Rough Design Up Front (RDUF) is something in between being totally pragmatic with the system design and being too strict about it. RDUF helps getting the ball rolling faster and provides some guidance to reduce premature optimizations and inform higher-level architectural decisions (which are difficult and expensive to change later on). 

## 6- DRY: don’t repeat yourself
Reduce repetition of code.

## 7- Composition over inheritance
Considering how front-end development is flexible and require changes frequently, it’s better compose component and elements rather than using inheritance which makes things more strict and harder to move around

## 8- File Organization
Have a clear idea and system for organizing your project files depending on the project context and requirements, the main idea here is to have a conscious decisions how things are organized.

## 9- Data formats and structure
Define the data format at the beginning of the project, and plan well to avoid over-/under fetching. Keep the front-end lean and move the heavy lifting to the back-end to provide the final data to the front-end. Consider using technologies like GraphQL. Don’t forget to minimize the number of HTTP requests to improve the performance.
- consider sizing (especially when you’re dealing with large project, a small piece of unnecessary information or decision about data format, ex: .json can have huge implications / impact on performance.)

## 10- Data flow
Define the data flow of the applications (bi-directional or one-directional) at the beginning and make it visible. Consider the size of the project and responsibilities of the different components.

## 11- System components
Abstract the systems’ configurations into their own files, ex:
env vars (API keys, endpoints, ..etc.)
Deployment flows and strategies (ex: turning off certain test-environments features ..etc.)
Theming options
Specific code of configurations of features and translations ..etc. 

## 12- Exception handling
Have a clear strategy how to deal with exceptions for the most important features and dedicate time to implement them (this part is usually forgotten and no one feels responsible to plan)

## 13- Execution strategies
Decide on how the system will be executed, ex:
Server side rendering (SSR) Vs Client side rendering (CSR)
Eager loading vs lazy loading ..etc.
