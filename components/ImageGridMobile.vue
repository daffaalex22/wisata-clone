<template>
    <v-container class="px-0 py-0">
        <v-row class="image-layout">
            <v-col :cols="9" :class="`image-layout-item`">
                <v-img :src="`${roomImages[0].size_sm}`" cover height="100%" :class="`image-item-${idx}`">
                    <v-btn v-if="!idx" class="see-photos-btn text-capitalize" size="small">
                        <v-icon start icon="mdi-grid"></v-icon>
                        See Photos
                    </v-btn>
                </v-img>
            </v-col>

            <v-col cols="3" class="d-flex flex-column">
                <v-row>
                    <v-col v-for="(image, childIdx) in childImages" :key="childIdx" :cols="12" class="pa-0">
                        <v-img :src="image.size_sm" cover height="100%"></v-img>
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>

<script setup>
const imageLayout = [{ cols: 9 }, { children: [{ cols: 12 }] }, { children: [{ cols: 12 }] }, { children: [{ cols: 12 }] }]
const props = defineProps({
    offer: Object
})

const roomImages = props.offer[0].room_images.slice(0, 4);
const childImages = roomImages.slice(1, 4);

</script>

<style scoped>
.image-layout-item {
    padding: 1px;
}

.image-item-1 {
    border-radius: 0 0 0 10px;
}

.image-item-3 {
    border-radius: 0 0 10px 0;
}

.see-photos-btn {
    position: absolute;
    left: 9%;
    bottom: 14%;
    z-index: 1000;
}
</style>