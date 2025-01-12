# Vue.Js Interview Questions.
In this repository, I have listed some Vue.js Interview Questions and their answer. <br />

1. [What is Vue.js?](#what-is-react-js) <br />
2. [Mention some of the features of Vue.js.](#mention-some-of-the-features-of-vuejs) <br />
2. [What are filters in Vue.js?](#mention-some-of-the-features-of-vuejs) <br />



### What is Vue.js?
  Vue is an open-source, progressive JavaScript framework for building user interfaces. Vue is a framework and ecosystem that covers most of the common features needed in front-end development. Using the Vuejs, we can develop websites and Single-Page Application (SPA).


### Mention some of the features of Vue.js.
  Templates <br />
	Event Handling <br />
	Routing  <br />
	Data Binding  <br />
	Light-weight nature  <br />
  Virtual DOM <br />
  Components <br />
  Simple integration and so on... 


  
### What are filters in Vue.js?
   Vue.js allows you to define filters that can be used to apply common text formatting. <br />
   Filters are usable in two places: mustache interpolations and v-bind expressions (the latter supported in 2.1.0+). 
   Filters should be appended to the end of the JavaScript expression, denoted by the “pipe”

 ```javascript
<!-- in mustaches -->
	{{ message | capitalize }}

	<!-- in v-bind -->
	<div v-bind:id="rawId | formatId"></div>
```
There are two types of filters. 
##### 1. Local Filters. <br />
   You can define local filters in a component’s options:
```javascript
      filters: {
	  capitalize: function (value) {
		if (!value) return ''
		value = value.toString()
		return value.charAt(0).toUpperCase() + value.slice(1)
	  }
      }
```
##### 2. Global Filters. <br />
   Define a filter globally before creating the Vue instance.
```javascript
    Vue.filter('capitalize', function (value) {
	  if (!value) return ''
	  value = value.toString()
	  return value.charAt(0).toUpperCase() + value.slice(1)
	})

     new Vue({
	  // ...
     })
```



