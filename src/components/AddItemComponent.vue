<template >
  <div>
    <div class="input-group">
      <input v-model="newItem" @keyup.enter="addItem" type="text" class="input form-control" placeholder="add shopping list item" />
      <span>
        <button @click="addItem" class="btn btn-defaul" type="button">Add!</button>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      newItem:''
    }
  },
  methods:{
    addItem(){
      var text
      text=this.newItem.trim()
      if(text){
        this.$emit('add', this.newItem)
        this.newItem=''
      }
    }
  }
}
</script>

<style>
</style>
