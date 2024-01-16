<template>
    <CatalogData :data="data" />

    <v-row justify="center">
        <v-col md="12" lg="10" class="px-1">
            <v-divider></v-divider>

            <v-tabs mandatory v-model="tab" color="primary" align-tabs="center">
                <v-tab :ripple="false" :key="1" :value="1"><span><v-icon end icon="mdi-tag-outline"></v-icon></span><span
                        class="px-auto ml-1 mr-2">Deals</span></v-tab>
                <v-tab :ripple="false" :key="2" :value="2"><span><v-icon end icon="mdi-grid"></v-icon></span><span
                        class="px-auto ml-1 mr-2">Photos</span></v-tab>
                <v-tab :ripple="false" :key="3" :value="3"><span><v-icon end
                            icon="mdi-information-outline"></v-icon></span><span
                        class="px-auto ml-1 mr-2">Info</span></v-tab>
            </v-tabs>

            <v-window v-model="tab">
                <v-window-item :value="1">
                    <Rooms :filters="filterSelection" />
                </v-window-item>

                <v-window-item :value="2">
                    Two
                </v-window-item>

                <v-window-item :value="3">
                    Three
                </v-window-item>
            </v-window>
        </v-col>
    </v-row>
</template>

<script setup>

import data from '~/static/dummy-data.json';

const tab = ref(null)

</script>

<style scoped></style>