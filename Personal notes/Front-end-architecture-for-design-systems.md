#CSS
Single Responsibility Principle: everything that is created for one single purpose.

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
In the preeeding code, any future change to the .primary-header will affect both elements, which reduces flexibility and can creates complications as the code grow larger.

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