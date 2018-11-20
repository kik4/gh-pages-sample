<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
    <Form />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import Form from "@/components/Form.vue"; // @ is an alias to /src

@Component({
  components: {
    HelloWorld,
    Form
  }
})
export default class Home extends Vue {}
</script>
