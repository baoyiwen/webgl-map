<template>
  <div></div>
</template>

<script lang="ts">
type c_webgl_props = {
    target: String;
}
import {Options, Vue} from "vue-class-component";
@Options({
    prop: {
        target: [String, HTMLElement],
    }
})
export default class Webgl extends Vue { 
    target!: String | HTMLElement;
    constructor(props: c_webgl_props) {
        super(props)
    }

    mounted() {
    }

    
}

</script>
