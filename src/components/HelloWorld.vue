<script setup>
import { ref, onMounted } from "vue";
import lottie from "lottie-web";
import a1 from "../public/loading.json";
import a2 from "../public/data.json";
import a3 from "../public/404.json";

defineProps({
  msg: String,
});

const count = ref(0);
onMounted(() => {
  const idFlow = document.getElementById("id-flow");
  const id404 = document.getElementById("id404");
  const idLoading = document.getElementById("id-loading");
  lottie.loadAnimation({
    container: idLoading,
    renderer: "svg",
    loop: true,
    autoplay: true,
    animationData: a1,
  });
  lottie.loadAnimation({
    container: idFlow,
    renderer: "svg",
    loop: true,
    autoplay: true,
    animationData: a2,
  });
  lottie.loadAnimation({
    container: id404,
    renderer: "svg",
    loop: true,
    autoplay: true,
    animationData: a3,
  });
});
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <div id="id-loading" style="width: 200px; height: 100%"></div>
  <div id="id-flow" style="width: 300px; height: 100%"></div>
  <div id="id404" style="width: 200px; height: 100%"></div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
