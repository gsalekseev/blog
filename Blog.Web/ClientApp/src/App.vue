<template>
    <v-app>
        <blog-navigation/>
        <blog-content/>
    </v-app>
</template>

<script>
    import BlogNavigation from './components/Navigation';
    import BlogContent from './components/Content';
    
    export default {
        name: 'App',
        components: {
            BlogNavigation,
            BlogContent
        },

        data: () => ({
            //
        })
    };
</script>

