<template>
    <v-row justify="center">
        <v-col cols="10" class="pb-0">
            <v-container>
                <v-row>
                    <v-col cols="4" class="pb-0">
                        <v-avatar size="180">
                            <v-img :src="data.catalog.hero_image_url.sm" alt="John" cover>
                            </v-img>
                        </v-avatar>
                    </v-col>

                    <v-col cols="8" class="pt-0 pb-0">
                        <v-container>
                            <v-row justify="start">
                                <v-col class="pt-0">
                                    <v-card variant="flat">
                                        <v-card-item>
                                            <div>
                                                <div class="text-h6 mb-1">
                                                    {{ data.name }}
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
                                                <div>
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

</script>

<style scoped></style>