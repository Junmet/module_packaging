<script>
export default {
  name: 'Content',
  data () {
    return {}
  },
  props: {
    datas: {
      type: Array,
      required: true
    }
  },
  render () {
    return (
      <div>
        {
          this.datas.map((item, index) => {
            // console.log(item.active);
            return <div>{item.active ? item.$slots.default : ''}</div>
          })
        }
      </div>
    )
  }
}
</script>
<style scoped>
</style>
