<template>
    <v-row justify="center">
        <v-col md="10" xs="12" class="pb-0">
            <v-container>
                <v-row justify="start">
                    <div class="d-flex d-sm-none">
                        <div class="text-h6 mb-1 px-3">
                            {{ data.name }}
                        </div>
                        <v-rating disabled v-model="starRating" color="orange-lighten-1" size="small" density="compact"
                            class="ml-1 pt-1" readonly half-increments empty-icon="star-outline" half-icon="mdi-star-half"
                            full-icon="mdi-star"></v-rating>
                    </div>
                </v-row>
                <v-row justify="end">
                    <v-col cols="4" class="pb-0 d-flex justify-center">
                        <v-container class="py-0">
                            <v-row justify="center">
                                <v-col xs="12" md="8" class="d-flex flex-column justify-center">
                                    <v-img :src="data.catalog.hero_image_url.sm" alt="John" cover aspect-ratio="1"
                                        max-width="100%" class="rounded-circle">
                                    </v-img>
                                </v-col>
                            </v-row>
                        </v-container>
                        <!-- <v-avatar size="x-large">
                            <v-img :src="data.catalog.hero_image_url.sm" alt="John" cover>
                            </v-img>
                        </v-avatar> -->
                    </v-col>

                    <v-col cols="8" class="pt-0 pb-0">
                        <v-container>
                            <v-row justify="start">
                                <v-col class="pt-0 pl-0">
                                    <v-card variant="flat">
                                        <v-card-item class="pl-0">
                                            <div>
                                                <div class="d-none d-sm-flex">
                                                    <div class="text-h6 mb-1">
                                                        {{ data.name }}
                                                    </div>
                                                    <v-rating disabled v-model="starRating" color="orange-lighten-1"
                                                        size="small" density="compact" class="ml-1 pt-1" readonly
                                                        half-increments empty-icon="star-outline" half-icon="mdi-star-half"
                                                        full-icon="mdi-star"></v-rating>
                                                </div>

                                                <div class="text-caption text-capitalize">{{ data.type }}</div>
                                                <div>
                                                    {{ data.catalog.address_full }}
                                                </div>
                                                <div class="my-3">
                                                    <v-progress-circular :model-value="reviewRating" :color="ratingColor">{{
                                                        reviewRating }}</v-progress-circular>
                                                    {{ ratingCategory }} ·
                                                    {{ data?.catalog?.review_count }} reviews
                                                </div>
                                                <div class="d-none d-sm-flex">
                                                    {{ data.general_info.descriptions.headline }}
                                                </div>
                                            </div>
                                        </v-card-item>
                                    </v-card>
                                </v-col>
                            </v-row>

                        </v-container>

                    </v-col>

                </v-row>
                <v-row justify="start">
                    <div class="d-flex d-sm-none px-3">
                        {{ data.general_info.descriptions.headline }}
                    </div>
                </v-row>
            </v-container>
        </v-col>
    </v-row>
</template>

<script setup>
const props = defineProps({
    data: String
})

const data = props.data

const reviewRating = data.catalog.review_rating
const ratingCategory = data?.catalog?.review_rating >= 90 ? "Excellent" : "Very Good"
const ratingColor = data?.catalog?.review_rating >= 90 ? "purple" : "green"
const starRating = data.catalog.star_rating

</script>

<style scoped></style>