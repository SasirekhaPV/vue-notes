# vue-notes
Personal documentation for Vue JS

## Section 1: Introduction

* Vue is a Javascript framework which allows you to build anything from small widgets that can be inserted in larger projects to medium or fullsize enterprise projects.
* Vue is quite small and lean in terms of file size compared to other Javascript frameworks.
* Vue is extendable, it can increase in size and functionality depending on what the project requires.
* The Vue project exports a Vue object. This is Vue object can be imported and is the core of your vue application. By importing this object you create a new Vue instance. These istances have one major job: control a piece of code which they render to the screen.

To call a new Vue instance you use the following code. The `el` property is reserved and takes a `string` as a value. With this string we specify which part of our HTML should be under control of this Vue instance. This means that you can change this code through the Vue instance. The `data` property specifies what data you want to use in this Vue instance.
```
new Vue({
  el: '#app',
  data: {
    title: 'Hello World'
  }
})
```
```
<div id="app">
  <p>{{ title }}</p>
</div>
```

* A `directive` is command/instruction that Vue will recognize in order to perform a certain task. eg: `v-on`
* `v-on:input="changeTitle"` is a directive that tells Vue to listen to an input event. When the event is triggered the changeTitle event will be fired.

Stating a `method` in Vue object allows you to call that method in the HTML. All properties you need can be accessed using the `this` keyword. Vue automatically passes the event object to said method.
```
new Vue({
  el: '#app',
  data: {
    title: 'Hello World'
  },
  Methods: {
    changeTitle: function(event){
      this.title = event.target.value;
    }
  }
})
```
```
<div id="app">
  <input type="text" v-on:input="changeTitle">
  <p>{{ title }}</p>
</div>
```
