<template>
    <v-container class="px-0 py-0">
        <v-row class="image-layout">
            <template v-for="(image, imgIdx) in imageLayout" :key="imgIdx">
                <v-col :cols="image.cols" :class="`image-layout-item`">
                    <v-img :src="`https://picsum.photos/500/300?image=${image.cols * 40}`" cover height="100%"
                        :class="`image-item-${imgIdx}`">
                        <v-btn v-if="!imgIdx" class="see-photos-btn text-capitalize" size="small">
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