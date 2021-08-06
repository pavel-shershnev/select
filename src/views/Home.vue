<template>
<Select 
  :options="options"
  @show="showContent"
  />
  <hr />
 <div class="card center "> <strong>контент из селекта: </strong>{{content.name}}</div>
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
