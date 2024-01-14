<template>
    <CatalogData />

    <v-row justify="center">
        <v-col cols="10">
            <v-divider></v-divider>

            <v-tabs v-model="tab" color="primary" align-tabs="center">
                <v-tab :value="1"><span><v-icon end icon="mdi-tag-outline"></v-icon></span><span
                        class="px-auto ml-1 mr-2">Deals</span></v-tab>
                <v-tab :value="2"><span><v-icon end icon="mdi-grid"></v-icon></span><span
                        class="px-auto ml-1 mr-2">Photos</span></v-tab>
                <v-tab :value="3"><span><v-icon end icon="mdi-information-outline"></v-icon></span><span
                        class="px-auto ml-1 mr-2">Info</span></v-tab>
            </v-tabs>
        </v-col>
    </v-row>

    <v-row justify="center">
        <v-col cols="10">
            <v-container>
                <v-row justify="center">
                    <span class="mt-2 mr-3 font-weight-medium"><v-icon start icon="mdi-filter-outline"></v-icon>Filter
                        rooms
                        by</span>

                    <v-chip v-if="filterSelection.length" color="primary" variant="outlined" @click="clearFilter"
                        class="mx-2 mt-2"><span class="px-auto ml-2">Clear
                            All</span><v-badge class="" color="info" :content="filterSelection.length"
                            inline></v-badge></v-chip>

                    <v-chip-group v-model="filterSelection" multiple>

                        <v-chip color="primary"><v-icon end icon="mdi-silverware-fork-knife"></v-icon><span
                                class="px-auto ml-3 mr-2 px-1">Free
                                Breakfast</span></v-chip>
                        <v-chip color="primary"><v-icon end icon="mdi-credit-card-check-outline"></v-icon><span
                                class="px-auto ml-3 mr-2 px-1">Free
                                Cancellation</span></v-chip>
                    </v-chip-group>

                </v-row>
            </v-container>
        </v-col>
    </v-row>
</template>

<script setup>
const filterSelection = ref([])

const clearFilter = () => {
    filterSelection.value = []
}

</script>