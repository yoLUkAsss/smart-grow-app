<template>
    <v-container>
        <v-row>
            <v-col>
                <SGMeasure :title="'Humedad'" :prefix="''" :suffix="'%'" :value="65" :icon="'mdi-water-percent'" :icon-color="'blue'"></SGMeasure>
            </v-col>
            <v-col>
                <SGMeasure :title="'Temperatura'" :prefix="''" :suffix="'&deg;C'" :value="24" :icon="'mdi-thermometer-high'" :icon-color="'red'"></SGMeasure>
            </v-col>
        </v-row>
    </v-container>
</template>