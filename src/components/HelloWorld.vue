
<script lang="ts">
import Vue from "vue";
import { VNode, VueConstructor } from "vue";


var HelloComponent = Vue.component('hello-component',{
    render: function(createElement): VNode {
        const name = this.$vnode.componentOptions.Ctor.$_customName || this.$vnode.componentOptions.Ctor.prototype.$_customName;

        console.log(name);
        return createElement(
            "h2", {}, this.$slots.default
        );
    }
})

HelloComponent.prototype.$_customName = 'MyName';
HelloComponent.$_customName = 'MyName';

export default HelloComponent
</script>