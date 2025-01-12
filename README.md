# Vue.Js Interview Questions.
In this repository, I have listed some Vue.js Interview Questions and their answer. <br />

1. [What is Vue.js?](#what-is-react-js) <br />
2. [Mention some of the features of Vue.js.](#mention-some-of-the-features-of-vuejs) <br />
3. [What are filters in Vue.js?](#what-are-filters-in-vuejs) <br />
4. [How to create an instance in Vue.js?](#how-to-create-an-instance-in-vuejs) <br />
5. [Vue js Built-in Directives.](#vue-js-built-in-directives) <br />



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
There are two types of filters.  <br />

 <strong>1. Local Filters.</strong> <br />
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
   <strong>2. Global Filters.</strong> <br />
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
   <strong>Note:</strong> When the global filter has the same name as the local filter, the local filter will be preferred.

### How to create an instance in Vue.js?
Every Vue application starts by creating a new Vue instance with the Vue function: <br />
<strong>1. Vue 2 Syntax.</strong> <br />
```javascript
    var vm = new Vue({
	        // options
	     })
```
<strong>2. Vue 3 Synbtax.</strong> <br />
```javascript
import { createApp, ref } from 'vue'

createApp({
  setup() {
	return {
	  count: ref(0)
	}
  }
}).mount('#app')
```

### Vue js Built-in Directives.
   1. v-for <br /> 
   2. v-show <br />
   3. v-if <br />
   4. v-else <br />
   5. v-bind <br />
   6. v-model <br />
   7. v-text <br /> 
   8. v-html <br /> 
   9. v-else-if <br />
   10. v-on <br />
   11. v-slot <br />
   12. v-pre <br />
   13. v-once <br />
     And so on are some of the inbuilt directives present in Vue.js.


