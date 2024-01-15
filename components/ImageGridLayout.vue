<template>
    <v-container class="px-0 py-0">
        <v-row class="image-layout">
            <!-- <h2>{{ offer }}</h2> -->
            <template v-for="(image, idx) in roomImages" :key="idx">
                <v-col :cols="imageLayout[idx]?.cols || 4" :class="`image-layout-item`">
                    <v-img :src="`${image.size_sm}`" cover height="100%" :class="`image-item-${idx}`">
                        <v-btn v-if="!idx" class="see-photos-btn text-capitalize" size="small">
                            <v-icon start icon="mdi-grid"></v-icon>
                            See Photos
                        </v-btn>
                    </v-img>

                </v-col>
            </template>
        </v-row>
    </v-container>
</template>

<script setup>
const imageLayout = [{ cols: 12 }, { cols: 4 }, { cols: 4 }, { cols: 4 }]
const props = defineProps({
    offer: Object
})

const roomImages = props.offer[0].room_images.slice(0, 4);

</script>

<style scoped>
.image-layout-item {
    padding: 1px;
}

.image-layout {
    border-radius: 20px;
}

.image-item-0 {
    border-radius: 10px 10px 0 0;
}

.image-item-1 {
    border-radius: 0 0 0 10px;
}

.image-item-3 {
    border-radius: 0 0 10px 0;
}

.see-photos-btn {
    position: absolute;
    left: 4%;
    bottom: 7%;
    z-index: 1000;
}
</style>