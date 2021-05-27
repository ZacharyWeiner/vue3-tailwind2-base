<template>
  <div class="flex-col items-center justify-center">
    <img class='mx-auto'  alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <!-- <BCCTest/> -->
    <RunTest />
    <tailwind-test />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import RunTest from '@/components/Tests/RunTest.vue'
//import BCCTest from "@/components/Tests/BCCTest.vue"
import TailwindTest from '@/components/Tests/TailwindTest.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    RunTest,
    //BCCTest,
    TailwindTest
  }
}
</script>