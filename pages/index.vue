<template>
  <div class="container">
      <div class="wrapper">
        <textarea name="" id="" v-model="value"></textarea>
        <ul>
          <li v-for="(item, index) in list" :key="index">{{item}}</li>
        </ul>
      </div>
      <button @click="formatBtnHandler">format</button>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  data(){
    return {
      value: '',
      list: []
    }
  },
  methods: {
    formatBtnHandler(){
      let fileText = this.value
      fileText = fileText.replace(/[\r\n]/g,"");
      const matchReg = /ZUIR.*?D=[1-9]\)/ig;
      const arr = fileText.match(matchReg)
      this.list = arr
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
}
.wrapper{
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
textarea{
  width: 600px;
  height: 700px;
}
ul{
  width: 600px;
  margin-left: 20px;
}
</style>
