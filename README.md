# vue-var
A Vue.js project with a renderless component to handle variables inside v-for loop

See an example [here](https://github.com/ajomuch92/vue-var/blob/main/dev/serve.vue).

### Install  

NPM:  
```bash
npm i --save vue-var
```

### Usage instructions  

Install the component globally

```javascript
import VueVar from 'vue-var';

Vue.use(VueVar);
```

Or import it inside your component

```javascript
import VueVar from 'vue-var';

export default {
  ...
  components: {
    VueVar
  }
  ...
}

```


And use it inside your components

## Attributes

| Prop      | Type | Required | Description |
|-----------|-----------|--------|----------|---------|
| data      |     Array, Object, Boolean, Number, String   |    yes  |  The variable to store inside the renderless component |



### Example

```html
<template>
  <ul>
    <vue-var v-for="item in items" :key="item" :data="myMethod(item)">
      <li slot="default" slot-scope="{data}">
        Item {{item}} | My Method {{data}} | {{data % 2 == 0 ? 'Pair':'Odd'}}
      </li>
    </vue-var>
  </ul>
</template>
```

```javascript
export default {
  name: 'MyComponent',
  components: {
    VueVar
  },
  data: () => ({
    items: [],
  }),
  created() {
    this.items = Array.from({length: 10}, (_, i) => i + 1);
  },
  methods: {
    myMethod(number) {
      return Math.pow(number, 2);
    }
  }
};
```