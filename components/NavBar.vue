<template>
    <v-row justify="center">
        <v-col cols="10">
            <v-app-bar scroll-behavior="elevate" class="app-bar">
                <v-container>
                    <v-row justify="center">
                        <v-col cols="1">

                        </v-col>
                        <v-col cols="2">
                            <v-app-bar-title>
                                <img src="~/assets/logo.png" alt="Wisata App Logo" class="logo" />
                            </v-app-bar-title>
                        </v-col>
                        <v-spacer></v-spacer>
                        <v-col cols="6">
                            <v-btn width="100%" class="search-bar mt-2 text-capitalize">
                                <v-icon icon="mdi-magnify"></v-icon>
                                The Langham, Jakarta · 25 - 26 Jun
                            </v-btn>
                        </v-col>
                        <v-spacer></v-spacer>
                        <v-col cols="2">
                            <v-btn class="mt-2 text-capitalize sign-in-btn">
                                Sign in
                            </v-btn>
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