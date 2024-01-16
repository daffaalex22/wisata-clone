<template>
    <v-container class="px-0 py-0">
        <v-row class="image-layout">
            <template v-for="(image, idx) in roomImages" :key="idx">
                <v-col v-if="imageLayout[idx]?.cols" :cols="imageLayout[idx]?.cols" :class="`image-layout-item`">
                    <v-img :src="`${image.size_sm}`" cover height="100%" :class="`image-item-${idx}`">
                        <v-btn v-if="!idx" class="see-photos-btn text-capitalize" size="small">
                            <v-icon start icon="mdi-grid"></v-icon>
                            See Photos
                        </v-btn>
                    </v-img>
                </v-col>

                <v-col v-if="imageLayout[idx]?.children" cols="3" class="d-flex flex-column">
                    <v-row>
                        <v-col v-for="(children, childIdx) in imageLayout[idx]?.children" :key="childIdx"
                            :cols="children.cols" class="pa-0">
                            <v-img :src="`https://picsum.photos/500/300?image=${children.cols + childIdx}`" cover
                                height="100%"></v-img>
                        </v-col>
                    </v-row>
                </v-col>

            </template>
        </v-row>
    </v-container>
</template>

<script setup>
const imageLayout = [{ cols: 9 }, { children: [{ cols: 12 }, { cols: 12 }, { cols: 12 }] }]
const props = defineProps({
    offer: Object
})

const roomImages = props.offer[0].room_images.slice(0, 4);

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