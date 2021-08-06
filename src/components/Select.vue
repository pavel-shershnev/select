<template>
  <div class="card" @click="click"><strong>{{selectedValue}}</strong></div>

  <div class="card b" v-if="visible">
    <p 
    @click ="clickOption(opt)"
    v-for="opt in options" 
    :key="opt.value" 
    >
    {{opt.name}}  
    </p>
  </div>


</template>

<script>
import {ref, onMounted} from 'vue'

export default {
  props: ['options'],
  setup(props, {emit}) {
  

    const visible = ref(false)
    const selectedValue = ref('')

      onMounted(() => {
      selectedValue.value = props.options[0].name
    })

    const click = () => {
      visible.value=!visible.value
    }
    const clickOption = (opt) => {
      selectedValue.value = opt.name
      emit('show',opt)
      visible.value = false
    }
    return {
      visible, click, selectedValue, clickOption
    }
  }
}
</script>


<style scoped lang="scss">
.card{
    width: 30%;
    margin: 0;
    cursor: pointer;
}
.card.b p:hover{
  background: rgba(4, 4, 4, 0.067)
}


</style>
