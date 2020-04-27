<template>
  <div>
    <div class="container">
      <div>this is old syntax</div>
      <header>
        <slot name="header">slot header</slot>
      </header>
      <main>
        <slot name='main'>slot main</slot>
      </main>
      <footer>
        <slot name="footer">slot footer</slot>
      </footer>
    </div>
    <div class="container">
      <div>this is new syntax v-slot</div>
      <header>
        <slot name="header-new">slot header</slot>
      </header>
      <main>
        <slot name='main-new'>slot main</slot>
      </main>
      <footer>
        <slot name="footer-new">slot footer</slot>
      </footer>
    </div>
    <section>
      <h2>scope slot</h2>
      <div class="container">
        <slot :user='user'>{{user.firstName}}</slot>

        <slot name='scope-test' :user='user'>{{user.firstName}}</slot>
        <slot name='scope-test-new' :user='user'>{{user.firstName}}</slot>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: '23452',
      user: {
        firstName: 'first',
        lastName: 'last'
      }
    }
  }
}
</script>
