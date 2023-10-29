<template>
    <v-container>
        <v-row>
            <v-col>
                <SGMeasure :title="'Humedad'" :prefix="''" :suffix="'%'" :topic="'esp32/humidity'" :icon="'mdi-water-percent'" :icon-color="'blue'"></SGMeasure>
            </v-col>
            <v-col>
                <SGMeasure :title="'Temperatura'" :prefix="''" :suffix="'&deg;C'" :topic="'esp32/temperature'" :icon="'mdi-thermometer-high'" :icon-color="'red'"></SGMeasure>
            </v-col>
        </v-row>

    </v-container>
</template>

<script>

export default {
    
}
</script>