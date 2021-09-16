<template>
    <div id="app">        
        <HelloVue></HelloVue>        
    </div>
</template>

<script>
    import HelloVue from './HelloVue.vue';

    export default {
        name: "App",
        components: {
            HelloVue
        },

        data() {
            return {
            }
        }
    };
</script>
