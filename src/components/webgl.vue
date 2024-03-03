<template>
  <div></div>
</template>

<script lang="ts">
type c_webgl_props = {
  target: String;
};
import { Options, Vue } from "vue-class-component";
@Options({
  prop: {
    target: [String, HTMLElement],
  },
})
export default class Webgl extends Vue {
 target!: String | HTMLElement;
  data() {
    return {};
  }

  // 组件的内部对象
  components: {};
  // 构造函数，用于初始化组件
  constructor(props: c_webgl_props) {
    super(props);
  }

  // 计算属性，用于计算组件的内部数据
  computed: {};

  // 组件挂载完成时调用
  mounted() {}

  // 组件创建完成时调用
  created() {}

  // 组件销毁时调用
  destroyed() {}

  // 组件更新时调用
  updated() {}

  // 渲染组件
  render() {}

  // 组件方法
  methods: {};

  // 组件观察属性
  watch: {};

}
</script>
