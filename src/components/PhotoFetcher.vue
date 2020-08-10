<template>
    <div>
        <b-container class="mt-4 container">
            <b-row class="mb">
                <b-col class="d-flex justify-content-start">
                    <h1>Photo Fetcher</h1>
                </b-col>
            </b-row>
            <b-row class="align-items-center mb">
                <b-col class="d-flex justify-content-start">
                    <b-form-checkbox class="align-self-end" v-model="grayscale" switch>
                        Make photos grayscale
                    </b-form-checkbox>
                </b-col>
                <b-col class="d-flex justify-content-end">
                    <b-button variant="primary" v-on:click="fetchNew">Fetch new photos</b-button>
                </b-col>
            </b-row>
            <b-row class="mb">
                <b-col class="d-flex justify-content-start">
                    <b-img class="w-100"
                           v-bind:src="imageSrc(1)"></b-img>
                </b-col>
                <b-col class="d-flex justify-content-end">
                    <b-img class="w-100"
                           v-bind:src="imageSrc(2)"></b-img>
                </b-col>
            </b-row>
            <b-row>
                <b-col class="d-flex justify-content-start">
                    <b-img class="w-100"
                           v-bind:src="imageSrc(3)"></b-img>
                </b-col>
                <b-col class="d-flex justify-content-end">
                    <b-img class="w-100"
                           v-bind:src="imageSrc(4)"></b-img>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script lang="ts">
    import {Component, Vue} from 'vue-property-decorator';

    @Component
    export default class PhotoFetcher extends Vue {
        grayscale = false;
        seed: Date = new Date();
        url = 'https://picsum.photos/seed/';
        isx = 350;
        isy = 255;


        imageSrc(index: number): string {
            return this.url + this.seed + index + '/' + this.isx + '/' + this.isy + (this.grayscale ? '?grayscale' : '');
        }

        fetchNew() {
            this.seed = new Date();
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .container {
        max-width: 750px
    }

    .mb {
        margin-bottom: 15px
    }

    button {
        font-size: 11px;
    }
</style>
