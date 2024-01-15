
<template>
    <v-row justify="center">
        <v-col cols="12">
            <v-container>
                <v-row v-for="(offer, key) in groupedData" :key="key">
                    <v-col cols="4">
                        <ImageGridLayout :offer="offer" />
                    </v-col>

                    <v-col cols="8" class="pt-0">
                        <RoomOptionLayout :offer="offer" />
                    </v-col>
                </v-row>
            </v-container>
        </v-col>
    </v-row>
</template>

<script setup>
import availabilityData from '~/static/dummy-availability.json'

const offerList = availabilityData.offer_list
var groupedData = {};

offerList.forEach(function (a) {
    groupedData[a.room_name] = groupedData[a.room_name] || [];
    groupedData[a.room_name].push(a);
});
</script>

<style scoped></style>