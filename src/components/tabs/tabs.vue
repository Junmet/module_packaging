
<script>
import Content from './content'
export default {
  name: 'Tabs',
  data () {
    return {
      // 承载content内容
      datas: []
    }
  },
  components: {
    Content
  },
  props: {
    currentIndex: {
      type: [String, Number],
      default: '1'
    }
  },
  methods: {
    onChangeIndex (index) {
      //   直接赋值是不可以的因为子组件是不可以修改父组件传递给子组件的props,有因为此事件是子组件触发
      //   this.currentIndex = index
      this.$emit('changeIndex', index)
    }
  },
  // this.$slots.default以插槽的形式读取tabs里面嵌套的内容
  render () {
    return (
      <div>
        <ul class="tabs-header">{this.$slots.default}</ul>
        <Content datas={this.datas} />
      </div>
    )
  }
}
</script>
<style scoped>
.tabs-header {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  border-bottom: 2px solid #ededed;
}
</style>
