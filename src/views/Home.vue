<template>

<div class="cont" >
 <div class="one">
    <Select 
    :options="options"
    @show="showContent"
    />
 </div>
  <!-- <hr /> -->
 <div class="card two"> 
   <strong>контент из селекта: </strong>
   {{content.name}}
 </div>
</div>
  
</template>

<script>
import Select from '@/components/Select.vue'

import {ref} from 'vue'

export default {
  setup(props) {
    const options = ref([
      {value: 'option 1', name: 'контент 1'},
      {value: 'option 2', name: 'контент 2'},
      {value: 'option 3', name: 'контент 3'},
    ])
    const content = ref({})

    const showContent = (opt)=>{
      return content.value = opt
    }
    return {
      options, showContent, content
    }
  },
  components: {Select}
}
</script>

<style scoped lang="scss">
.cont {display: flex; height: 300px;}
div

.one {
  width: 300px;
  padding-right: 10pt;
}
.two {
  width: 100%;
}


</style>