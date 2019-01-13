<template> 
  <div id="app" class="container"> 
    <h2>{{ title }}</h2> 
    <add-item-component v-on:add="addItemToItems"></add-item-component> 
    <items-component :items="items"></items-component> 
    <div class="footer"> 
      <hr/> 
      <change-title-component></change-title-component> 
    </div> 
  </div> 
</template> 


<script>
  import AddItemComponent from './components/AddItemComponent'
  import ItemsComponent from './components/ItemsComponent'
  import ChangeTitleComponent from './components/ChangeTitleComponent'

  export default{
    components:{
      AddItemComponent,
      ItemsComponent,
      ChangeTitleComponent,
    },
    data(){
      return{
        items:[{text:'Banana', checked:true},
               {text:'Appels', checked:false}]
      }
    },
    methods: { 
      addItemToItems (text) { 
        this.items.push({ 
          text: text, 
          checked: false 
        }) 
      } 
    } 
  }
  
</script>

<style>
</style>
