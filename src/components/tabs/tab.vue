<script>
export default {
  name: 'Tab',
  props: {
    label: {
      type: [String, Number],
      default: 'tab'
    },
    index: {
      type: [String, Number],
      default: '1'
    }
  },
  //   计算属性
  //  this.$parent.currentIndex可以拿到父组件得currentIndex值
  computed: {
    active () {
      return this.index === this.$parent.currentIndex
    }
  },
  //   钩子函数
  mounted () {
    //   当前组件有个高亮的判断（active）也就是说谁高亮就显示谁的内容，而不是全部内容显示出来，所以要把当前
    //   的active事件传递过去，直接传递this，this指的就是当前这个组件的实列（tab）
    // this.$parent.datas.push(this.$slots.default)
    this.$parent.datas.push(this)
  },
  methods: {
    // 点击事件
    clickTabHandler () {
      // 这个地方使用this.$emit是不可以的因为真的父子关系是App在搭建，而tabs只是封装效果，所以没办法绑定此事件
      // 调用父组件的onChangeIndex事件
      this.$parent.onChangeIndex(this.index)
    }
  },
  render () {
    const currentClass = {
      tab: true,
      active: this.active
    }
    // 因为点击得是tab栏所以给li标签添加点击事件
    return (
      <li class={currentClass} onClick={this.clickTabHandler}>
        {this.label}
      </li>
    )
  }
}
</script>
<style scoped>
.tab {
  flex: 1;
  list-style: none;
  line-height: 40px;
  margin-right: 30px;
  position: relative;
  text-align: center;
}

.tab.active {
  border-bottom: 2px solid blue;
}
</style>
