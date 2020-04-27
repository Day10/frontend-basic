<template>
  <div>
    <!-- <slot-component v-slot='scopeProp'> 默认slot如果没有其他具名插槽可以这么写，但是有其他具名插槽的时候，要用template语法，详细见column10 -->
    <slot-component>
      <div slot='header'>custome header</div>
      <!-- v-slot只能用在template上面 -->
      <template v-slot:header-new>header new</template>
      <template v-slot:main-new>main new</template>
      <template v-slot:footer-new>footer new</template>
      <template v-slot='scopeProp'>有其他具名插槽的时候，默认插槽用template语法{{scopeProp.user.lastName}}</template>
      <template slot='scope-test' slot-scope="scopeProp"><div>old syntax: {{scopeProp.user.lastName}}</div></template>
      <template v-slot:scope-test-new='scopeProp'>new syntax: {{scopeProp.user.lastName}}</template>
    </slot-component>
  </div>
</template>

<script>
import SlotComponent from './slot/index'
export default {
  name: 'HelloWorld',
  components: {
    SlotComponent
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>
