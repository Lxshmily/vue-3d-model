<template>
    <div class="demo-basic">
        <demo-block :code="code">
            <template slot="preview">
                <model-three :backgroundAlpha="0"
                    @on-load="onLoad"
                    src="static/models/json/scene.json"></model-three>
                <div class="example-loading" v-show="loading"></div>
            </template>
        </demo-block>
    </div>
</template>

<script>
import DemoBlock from '../components/demo-block';
import ModelThree from '../../src/model-three.vue'

const code = `

<template>
    <model-three src="static/models/json/scene.json"></model-three>
</template>

<script>
    import { ModelThree } from 'vue-3d-model'

    export default {
        components: {
            ModelThree
        }
    }
<\/script>

`

export default {
    name: 'demo-basic',
    data () {
    	return {
            code,
            loading: true
    	}
    },
    methods: {
        onLoad () {
            this.loading = false;
        }
    },
    components: {
        ModelThree,
        DemoBlock
    }
}
</script>
<style>
	.demo-basic {
        padding: 20px;
        background: #fff;
        box-shadow: 0 2px 4px 0 rgba(0,0,0,.1), 0 16px 24px 0 rgba(81,129,228,.1);
	}
</style>
