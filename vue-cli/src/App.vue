<template>
  <div>
    {{ str }}
<!--    v-bind:하위 컴포넌트 props="상위(현재) 컴포넌트 data"-->
<!--    v-on:하위 컴포넌트 emit or method동작="상위(현재) 컴포넌트 메소드"-->
    <app-header
        v-bind:propsdata="str"
        v-on:emitTest="renewStr"></app-header>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";

export default {
  components: {
    'app-header': AppHeader
  },
  data() {
    return {
      str: 'Header!!',
    };
  },
  methods: {
    renewStr(){
      this.str = 'hi';
    }
  },
}
</script>

<style>

</style>
