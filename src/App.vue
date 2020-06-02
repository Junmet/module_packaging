<template>
  <tabs :currentIndex="currentIndex" @changeIndex="changeIndexHandler">
    <tab label="tab1" index="1">
       <div>我是内容1</div>
    </tab>
    <tab label="tab2" index="2">
       <div>我是内容2</div>
    </tab>
    <tab label="tab3" index="3">
       <div>我是内容3</div>
    </tab>
  </tabs>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      currentIndex: '1'
    }
  },
  methods: {
    changeIndexHandler (index) {
      this.currentIndex = index
    }
  }
}
</script>

<style scoped>

</style>
