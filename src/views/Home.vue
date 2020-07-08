<template>
  <div class="Home">
    The home view
    <HelloWorld msg="This is a prop! This gets data from the parent!" /><br>
    <b>Same Hello world component but we use a variable this time:</b>
    <HelloWorld :msg="foo" />
    <div>
      <button @click="upVariable">Click me!</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue";

@Component({
  components: {
    HelloWorld
  }
})
export default class Home extends Vue {
  private foo = 0;

  mounted() {
    console.log("This runs when this class is activated!");
    this.upVariable();
  }

  upVariable() {
    // This is a function that can be run via mounted or other events.
    console.log("SetVariable function is run!");
    this.foo++;
  }
}
</script>

<style scoped></style>
