<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <input v-model="inputvalue" />
    <button class="button" @click="handleAddItem">commit</button>
  </div>
  <ul>
    <list-item v-for="(item, index) in list"
    :key="index"
    :msg="item" />
  </ul>
</template>

<script>
import { reactive, ref } from 'vue'
import ListItem from './components/ListItem.vue'

export default {
  name: 'App',
  components: {ListItem},
  setup(){
    const inputvalue = ref('')
    const list = reactive([])

    const handleAddItem = () =>{
      list.push(inputvalue.value);
      inputvalue.value = ''
    }
  return { handleAddItem, inputvalue, list }
  }

  // components: {
  //   HelloWorld
  // }
}
</script>

<style>
.button {
  color: #d98185;
  margin-left: 20px;
}
</style>
