
<script lang="ts">
import Vue from "vue";
import { VNode, VueConstructor } from "vue";

var myMixin = {

    props: {
        blogTitle: String
    },
    methods: {
        hello: function () {
            console.log('Hello!')
        }
  }
}

// определяем компонент, использующий примесь
var MyComponent = Vue.component('my-component',{
    render: function(createElement): VNode {
        return createElement(
            "div", this.blogTitle
        );
    },
    props: {
        blogTitle: String
    }
})


MyComponent.prototype.$_customName = "customName";

export default MyComponent
</script>