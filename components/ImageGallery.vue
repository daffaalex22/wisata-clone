<template>
    <v-row class="mt-2">
        <v-col v-for="image in imageUrls" :key="image" class="d-flex child-flex" md="4" sm="6" xs="12">
            <v-img :src="image" :lazy-src="image" aspect-ratio="1" cover class="bg-grey-lighten-2">
                <template v-slot:placeholder>
                    <v-row class="fill-height ma-0" align="center" justify="center">
                        <v-progress-circular indeterminate color="grey-lighten-5"></v-progress-circular>
                    </v-row>
                </template>
            </v-img>
        </v-col>
    </v-row>
</template>

<script setup>
const { images } = defineProps({
    images: Array
})

const imageUrls = []

images.forEach(function (image) {
    imageUrls.push(image.url.sm)
});

</script>

<style scoped></style>