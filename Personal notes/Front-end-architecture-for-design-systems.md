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
