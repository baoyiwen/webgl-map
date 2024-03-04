<template>
	<div class="root-panel"></div>
</template>
<script lang="ts">
	import Webgl from "../components/webgl.vue";
	import { Options, Vue } from "vue-class-component";
	@Options({
		components: {
			Webgl,
		},
	})
	export default class Layout extends Vue {
		constructor() {
			super();
		}
	}
</script>
<style lang="less" scoped></style>
