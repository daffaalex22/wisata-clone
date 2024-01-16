
<template>
    <v-container>
        <v-row justify="center" class="mb-1 mt-1">
            <span class="mt-2 mr-3 font-weight-medium"><v-icon start icon="mdi-filter-outline"></v-icon>Filter
                rooms
                by</span>

            <v-chip v-if="filterSelection.length" color="primary" variant="outlined" @click="clearFilter"
                class="mx-2 mt-2"><span class="px-auto ml-2">Clear
                    All</span><v-badge class="" color="info" :content="filterSelection.length" inline></v-badge></v-chip>

            <v-chip-group v-model="filterSelection" multiple>
                <v-chip variant="outlined" color="primary"><v-icon end icon="mdi-silverware-fork-knife"></v-icon><span
                        class="px-auto ml-3 mr-2 px-1">Free
                        Breakfast</span></v-chip>
                <v-chip variant="outlined" color="primary"><v-icon end icon="mdi-credit-card-check-outline"></v-icon><span
                        class="px-auto ml-3 mr-2 px-1">Free
                        Cancellation</span></v-chip>
            </v-chip-group>

        </v-row>
    </v-container>
    <v-row>
        <v-col xs="12">
            <v-container>
                <v-row class="d-none d-sm-flex" justify="space-between" v-for="(offer, key) in groupedData" :key="key">
                    <v-col sm="4">
                        <ImageGridLayout :offer="offer" />
                    </v-col>

                    <v-col class="pt-0">
                        <RoomOptionLayout :offer="offer" />
                    </v-col>
                </v-row>
                <v-row class="d-flex d-sm-none" justify="end" v-for="(offer, key) in groupedData" :key="key">
                    <v-col class="py-0 px-0" cols="12">
                        <RoomOptionMobile :offer="offer" />
                    </v-col>
                </v-row>
            </v-container>
        </v-col>
    </v-row>
</template>

<script setup>
// import availabilityData from '~/static/dummy-availability.json'

const getIdFromSlug = (slug) => {
    const slugArray = slug.split("-");
    return slugArray[slugArray.length - 1]
}

const { slug } = useRoute().params
const id = getIdFromSlug(slug)
const query = useRoute().query

const { data: dataFromAPI } = await useFetch('https://exterior-technical-test-api.vercel.app/property/availability/' + id, { query })
const availabilityData = toRaw(dataFromAPI.value)


import { useDisplay } from 'vuetify'

const { xs, md } = useDisplay();

const filterSelection = ref([])

const clearFilter = () => {
    filterSelection.value = []
}

const offerList = ref(null)
offerList.value = availabilityData.offer_list

const groupedData = ref({});

offerList.value.forEach(function (a) {
    groupedData.value[a.room_name] = groupedData.value[a.room_name] || [];
    groupedData.value[a.room_name].push(a);
});

const originalGroupedData = { ...groupedData.value }

watch(filterSelection, (newFilters) => {
    groupedData.value = {}
    if (!newFilters?.length) {
        groupedData.value = { ...originalGroupedData }
        return
    }

    offerList.value.forEach(function (a) {
        if (newFilters.includes(0) && !a.meal_plan_description) return
        if (newFilters.includes(1) && a.cancel_policy_code == "NR") return
        groupedData.value[a.room_name] = groupedData.value[a.room_name] || [];
        groupedData.value[a.room_name].push(a);
    });
})

</script>

<style scoped></style>