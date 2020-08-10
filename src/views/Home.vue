<template>
    <div>
        <PhotoFetcher/>
    </div>
</template>

<script>
    import PhotoFetcher from '@/components/PhotoFetcher.vue'

    export default {
        name: 'Home',
        components: {
            PhotoFetcher: PhotoFetcher
        }
    }
</script>
