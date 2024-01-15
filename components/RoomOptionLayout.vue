<template>
    <v-table class="rounded-lg border mb-4">
        <thead>
            <tr>
                <th class="text-left py-2">
                    <p class="text-h6 font-weight-medium">
                        {{ offer[0].room_name }}
                    </p>

                    <v-icon color="grey" icon="mdi-bed-king-outline" size="small">
                    </v-icon>
                    <span class="font-weight-regular ml-1"> {{ offer[0].room_bed_groups }} </span>

                    <v-icon color="grey" icon="mdi-image-size-select-small" class="ml-2" size="small">
                    </v-icon>
                    <span class="font-weight-regular ml-1"> {{
                        offer[0].room_size_sqm
                    }} m<sup>2</sup> </span>
                </th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <v-card v-for="item in offer" :key="item.offer_id" width="100%" class="rounded-0 table-item" variant="flat">
                    <v-card-text class="py-0">
                        <v-row align="start" no-gutters>
                            <v-col cols="6">
                                <div class="my-3">
                                    <p>
                                        <v-icon start icon="mdi-silverware-fork-knife"></v-icon>Without breakfast
                                    </p>
                                    <p class="text-red">
                                        <v-icon start icon="mdi-credit-card-off-outline">
                                        </v-icon>Non Refundable
                                    </p>
                                </div>

                                <v-chip class="my-2 rounded-0 py-0 px-2" variant="flat" color="red">
                                    <h5 class="py-0 font-weight-medium">
                                        SAVE <span class="font-weight-bold">{{
                                            Math.round(item.pricing_data.saving_pct * 100) }}%</span> TODAY!
                                    </h5>
                                </v-chip>

                                <p class="text-disabled text-decoration-line-through">
                                    {{ moneyFormatter(item.pricing_data.strikethrough_rate_nightly) }}
                                </p>
                                <h3 class="font-weight-regular my-1">
                                    Rp <span class="font-weight-medium">{{ moneyFormatter(item.pricing_data.rate_nightly,
                                        "decimal")
                                    }}</span> /
                                    night
                                </h3>
                                <p class="text-disabled">after tax and fees *</p>

                                <p class="text-disabled text-caption my-3">
                                    * Member-only price, valid in app only
                                </p>
                            </v-col>

                            <v-col cols="6" class="text-right d-flex flex-column">
                                <v-row justify="end">
                                    <v-col class="my-3" cols="12">
                                        <v-btn size="x-small" elevation="0" start icon="mdi-content-copy"><template v-slot:>
                                                <v-icon size="large" color="grey"></v-icon></template></v-btn>
                                        <v-btn size="x-small" elevation="0" start icon="mdi-fullscreen"><template v-slot:>
                                                <v-icon size="x-large" color="grey"></v-icon></template></v-btn>
                                        <v-btn size="x-small" elevation="0" start icon="mdi-dots-horizontal"><template
                                                v-slot:>
                                                <v-icon size="x-large" color="grey"></v-icon></template></v-btn>
                                    </v-col>

                                    <v-col cols="12">
                                        <v-btn class="text-capitalize" color="#007aff" elevation="0">
                                            Book Now
                                        </v-btn>

                                        <p class="text-blue text-caption my-3" color="#007aff">
                                            <v-icon size="x-small" color="blue" icon="mdi-star"></v-icon>
                                            Collect 3 points
                                        </p>
                                    </v-col>
                                </v-row>
                            </v-col>
                        </v-row>
                    </v-card-text>
                </v-card>
            </tr>
        </tbody>
    </v-table>
</template>

<script setup>
const props = defineProps({
    offer: Object
})

const moneyFormatter = (number, style = "currency") => {
    const money = new Intl.NumberFormat('id-ID', { style, currency: "IDR", maximumFractionDigits: 0, }).format(number)

    const result = money.replaceAll('.', ',')

    return result
}

</script>

<style scoped>
.table-item {
    border-style: solid;
    border-width: 0 0 1px 0;
}

.table-item:last-of-type {
    border-style: none;
}
</style>