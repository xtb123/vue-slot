// 子组件 默认插槽
<!--<template>-->
<!--<div class="content">-->
<!-- 默认插槽-->
<!--<header class="text">-->
<!--&lt;!&ndash; slot 的后备内容：为一个插槽设置具体后备（默认）内容是很有用的，当父组件不添加任何插槽内容时，默认渲染该后备内容的值。 &ndash;&gt;-->
<!--<slot>默认值</slot>-->
<!--</header>-->
<!--</div>-->
<!--</template>-->

// 子组件 具名插槽
<!--<template>-->
<!--<div class="content">-->
<!--&lt;!&ndash; 具名插槽 &ndash;&gt;-->
<!--<main class="text">-->
<!--<slot name="main"></slot>-->
<!--</main>-->
<!--<footer class="text">-->
<!--<slot name="footer">123</slot>-->
<!--</footer>-->
<!--</div>-->
<!--</template>-->

<!--父组件 作用域插槽-->
<template>
  <div class="content">
    <!-- 作用域插槽,以及解构插槽Prop的写法 -->
    <footer class="text">
      <slot name="footer" :user="user" :testClick="testClick">
        {{user.name}}
      </slot>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'child',
  data () {
    return {
      user: {
        title: '测试title',
        name: '测试name'
      }
    }
  },
  methods: {
    testClick () {
      // 子组件通用方法，可传递给父组件复用
      alert('123')
    }
  }
}
</script>
