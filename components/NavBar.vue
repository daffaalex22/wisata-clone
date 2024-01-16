<template>
    <v-row justify="center">
        <v-col cols="10">
            <v-app-bar scroll-behavior="elevate" class="app-bar">
                <v-container>
                    <v-row justify-xs="center" justify-md="center">
                        <v-col xs="2" md="1">
                            <v-btn class="d-flex d-sm-none" size="large" icon="mdi-chevron-left" ripple="false">
                                <template v-slot:>
                                    <v-icon size="x-large" color="#007aff"></v-icon></template>
                            </v-btn>
                        </v-col>
                        <v-col class="d-none d-sm-flex" cols="2">
                            <v-app-bar-title>
                                <NuxtLink to="https://wisata.app">
                                    <img src="~/assets/logo.png" alt="Wisata App Logo" class="logo" />
                                </NuxtLink>
                            </v-app-bar-title>
                        </v-col>
                        <v-spacer class="d-none d-sm-flex"></v-spacer>
                        <v-col xs="10" md="6">
                            <v-btn width="100%" class="search-bar mt-2 text-capitalize">
                                <v-icon icon="mdi-magnify"></v-icon>
                                The Langham, Jakarta · 25 - 26 Jun
                            </v-btn>
                        </v-col>
                        <v-spacer></v-spacer>
                        <v-col cols="1">
                            <v-btn class="mt-2 text-capitalize sign-in-btn">
                                Sign in
                            </v-btn>
                        </v-col>
                        <v-col xs="2" sm="1">

                        </v-col>
                    </v-row>
                </v-container>
            </v-app-bar>
        </v-col>
    </v-row>
</template>

<script setup>

</script>

<style scoped>
.logo {
    height: auto;
    width: 185px;
}

.sign-in-btn {
    background-color: #007aff;
    color: white;
}

.search-bar {
    /* font-weight: 450; */
    background-color: #f5f5f5;
    letter-spacing: 0.1px;
}
</style>