# Vue.Js Interview Questions.
In this repository, I have listed some Vue.js Interview Questions and their answer. <br />

1. [What is Vue.js?](#what-is-react-js) <br />
2. [Mention some of the features of Vue.js.](#mention-some-of-the-features-of-vuejs) <br />
3. [What are filters in Vue.js?](#what-are-filters-in-vuejs) <br />
4. [How do I create an instance in Vue.js?](#how-to-create-an-instance-in-vuejs) <br />
5. [Vue js Built-in Directives.](#vue-js-built-in-directives) <br />
6. [What are the props in Vue.js?](#what-are-the-props-in-vuejs) <br />
7. [What are slots in Vue.js?](#what-are-slots-in-vuejs) <br />
8. [What are the difference between Created() and Mounted() in Vue js?](#what-are-the-difference-between-created-and-mounted-in-vue-js) <br />




### What is Vue.js?
Vue is an open-source, progressive JavaScript framework for building user interfaces. Vue is a framework and ecosystem that covers most of the common features needed in 
    front-end development. Using the Vuejs, we can develop websites and Single-Page Application (SPA).


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

### What are the props in vue.js?
   Props in Vue is a way to pass values as attributes to child components
   
   In SFCs using <script setup>, props can be declared using the defineProps() macro:
```javascript
   <script setup>
	const props = defineProps(['foo'])
	console.log(props.foo)
   </script>
```
In non-<script setup> components, props are declared using the props option:

```javascript
   export default {
	  props: ['foo'],
	  setup(props) {
		// setup() receives props as the first argument.
		console.log(props.foo)
	  }
   }
```

### What are slots in vue.js?
Using Slot, We can  pass a template fragment to a child component from the parent, and let the child component render the fragment within its own template.
    For example, we may have a <Button> component that supports usage like this:
    
```javascript
<Button>
  Click me! <!-- slot content -->
</Button>
```
The template of ``<Button>`` looks like this:

```javascript
<button class="btn btn-success">
  <slot></slot> <!-- slot outlet -->
</button>
```


### What are the difference between Created() and Mounted() in Vue js?
In Vue.js, the created() method is called after a component is created, but before it's added to the page. The mounted() method is called after the component's DOM is created and added to the page.

<strong>When to use created() </strong>
1. Fetch data from an API
2. Manipulate data passed in via props
3. Trigger actions like data fetching from an API backend

<strong>When to use mounted()  </strong>
1. Load anything that manipulates the component's DOM
2. Access the reactive component, templates, and DOM elements.

<strong>What's different about created() and mounted() </strong>
1. created() is called before mounted()
2. You can't perform DOM manipulations in created() because the DOM hasn't been mounted yet
3. mounted() is the most often used hook in the lifecycle

