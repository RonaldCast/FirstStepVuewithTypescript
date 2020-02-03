<template>
  <div id="app">
    <Header @handleSearch="searchPost"></Header>
  </div>
</template>

<script lang="ts">
import {Vue, Component} from 'vue-property-decorator';
import Header from "@/components/Header.vue";

@Component({
  name: "app",
  components:{
    Header
  }
})
export default class App extends Vue{

  private searchPost(value : string) : void {
    console.log(value)
  }
}


</script>
<style lang="scss">
*, *::before, *::after{
  margin: 0;
  padding: 0px;
  box-sizing: border-box;
}
</style>
