<template>
    <v-row justify="center">
        <v-col cols="10" class="pb-0">
            <v-container>
                <v-row>
                    <v-col cols="4" class="pb-0">
                        <v-avatar size="180">
                            <v-img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John">
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
                                                    Hotel
                                                </div>
                                                <div class="text-caption">Hotel</div>
                                                <div>
                                                    District 8 SCBD Lot 28, Jakarta, Indonesia
                                                </div>
                                                <div class="my-3">
                                                    <v-progress-circular model-value="60"
                                                        color="brown"></v-progress-circular>
                                                    Excellent ·
                                                    17 reviews
                                                </div>
                                                <div>
                                                    Business, romantic, city hotel with spa, shopping facilities in Jakarta
                                                    (Senayan)
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

</script>

<style scoped></style>