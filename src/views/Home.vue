<template>
    <div class="home">
        <div class="links" ref="links">
            <router-link to="hello" tag="li">Hello</router-link>
            <router-link to="About" tag="li">About</router-link>
            <router-link to="Search" tag="li">Search</router-link>
        </div>
        <router-view></router-view>
    </div>
</template>

<script lang="ts">
    import Vue from 'vue';
    import Component from 'vue-class-component';

    @Component
    export default class Home extends Vue {
        name = 'hello';
        $refs!: {
            links: HTMLElement;
        }
        mounted() {
            console.log((this.$refs.links as HTMLElement).style);
        }
    };
</script>

<style lang="scss" scoped>
    .home {
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0; // background-color: #4DBA87;
    }

    .links {
        cursor: pointer;
        margin-top: 20px;
    }

    .router-link-exact-active,
    .router-link-active {
        color: #4DBA87;
    }

</style>
