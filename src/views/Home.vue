<template>
    <div>
        <PhotoFetcher/>
    </div>
</template>

<script>
    // @ is an alias to /src
    import PhotoFetcher from '@/components/PhotoFetcher.vue'

    export default {
        name: 'Home',
        components: {
            PhotoFetcher: PhotoFetcher
        }
    }
</script>
