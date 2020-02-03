<template>
    <div class="header">
        <input v-model="search" type="text" placeholder="Search post" class="header__input header__input--search" >
    </div>
</template>
<script lang="ts"> 
import {Vue, Component, Emit, Watch} from 'vue-property-decorator'

@Component({
    name: "Header"
})
export default class Header extends Vue{
private search : string = "";
@Emit('handleSearch')
handleSearch() : string{
    return this.search;
}

@Watch("search",{immediate: true, deep:true })
searchPost(){
  this.handleSearch();
}

}
</script>
<style lang="scss">
@import "../assets/variable";
    .header{
        text-align: center;
        background: $BlueDark;
        padding: 20px
    }
    .header__input--search{
        border: none;
        font-size: $fontBody * 1em;
        padding: 15px;
        width: (100% / 2);
        max-width: (1200px /2);
        border-radius: 7px;
        background: $Blueligth;

    }
</style>