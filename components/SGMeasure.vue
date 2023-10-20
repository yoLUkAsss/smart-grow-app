<template>
    <div>
        <v-card :title="title" width="400px" height="200px">
            <v-card-text class="py-0">
                <v-row align="center" no-gutters>

                    <v-col class="text-h2" cols="6" >
                        {{prefix + " " + value + " " + suffix}} 
                    </v-col>

                    <v-col cols="6" class="text-right">
                        <v-icon :color="iconColor" :icon="icon" size="88" />
                    </v-col>

                </v-row>
            </v-card-text>
        </v-card>
    </div>
</template>

<script>

export default {
    props: {
        title: {
            type: String
        },
        prefix: {
            type: String
        },
        value: {
            type: Number
        },
        suffix: {
            type: String
        },
        icon: {
            type: String
        },
        iconColor: {
            type: String
        }
    },
    data: () => ({
    //   value: 24
    }),
  }

</script>