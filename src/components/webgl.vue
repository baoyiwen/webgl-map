<template>
	<div class="canvas-root">
		<canvas
			class="canvas-context"
			ref="canvasElements"
		>
		</canvas>
	</div>
</template>

<script lang="ts">
	type c_webgl_props = {
		target: string | HTMLElement;
		width: number;
		height: number;
	};
	import { Options, Vue } from "vue-class-component";
	import { ref, Ref } from "vue";
	@Options({
		prop: {
			target: [String, HTMLElement],
			width: Number,
			height: Number,
		},
	})
	export default class Webgl extends Vue {
		target!: string | HTMLElement;
		width!: number;
		height!: number;

		private canvasElements!: Ref<HTMLCanvasElement | null>;
		private mutationObserver!: MutationObserver;
		// 构造函数，用于初始化组件
		constructor(props: c_webgl_props) {
			super(props);
			this.init();
			this.canvasElements = ref<HTMLCanvasElement | null>(null);
			this.mutationObserver = new MutationObserver((ele) => {
				this.getCanvasWarpSize();
			});
		}

		// 初始化组件
		init() {
			// 初始化画布和webgl上下文
			this.width = 500;
			this.height = 500;
		}

		private get dealWidth() {
			return this.width - 20;
		}

		private get dealHeight() {
			return this.height - 20;
		}

		private getCanvasWarpSize() {
			return null;
		}

		// 组件挂载完成时调用
		mounted() {}

		beforeMount(): void {
			// // 监听目标元素的变化
			// this.mutationObserver.observe(this.target, {
			//   attributes: true, // 监听属性变化
			//   attributeFilter: ["style", "class"], // 监听特定属性
			//   childList: true, // 监听子节点变化
			//   subtree: true, // 监听后代节点变化
			// });
		}

		// 组件创建完成时调用
		created() {}

		// 组件销毁时调用
		destroyed() {
			// 移除监听
			this.mutationObserver.disconnect();
		}

		// 组件更新时调用
		updated() {}

		// 渲染组件
		render() {}

		// 组件观察属性
	}
</script>

<style scoped lang="less">
	.canvas-root {
		width: 100%;
		height: 100%;
		box-sizing: border-box;
	}

	.canvas-context {
		width: 100%;
		height: 100%;
	}
</style>
