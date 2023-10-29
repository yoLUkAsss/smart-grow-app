<template>
    <div>
        <v-card :title="title" width="400px" height="200px">
            <v-card-text class="py-0">
                <v-row align="center" no-gutters>

                    <v-col class="text-h3   " cols="8" >
                        {{prefix + " " + value + " " + suffix}} 
                    </v-col>

                    <v-col cols="4" class="text-right">
                        <v-icon :color="iconColor" :icon="icon" size="88" />
                    </v-col>

                </v-row>

            </v-card-text>
        </v-card>
    </div>
</template>

<script>
import * as mqtt from 'mqtt/dist/mqtt.min'


export default {
    data: () => ({
        value: 0
    }),

    props: {
        title: {
            type: String
        },
        prefix: {
            type: String
        },
        topic: {
            type: String
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

    mounted () {

        let vm = this
        console.log(`Topic: ${vm.topic}`)

        let options = {
            clean: false,
            keepalive: 60,
            clientId: "client-id-" + Math.random().toString(16).substring(2, 10),
            connectTimeout: 4000,
        }
        let client = mqtt.connect("ws://localhost:9001", options)
        

        client.on("connect", function () {
            console.log("CONNECTED")
            client.subscribe(vm.topic, (err) => {
                if (!err) {
                    // console.log("SUBSCRIPTO")
                } else {
                    console.error(`Error ocurred: ${err}`)
                }
            })
        })

        client.on("message", function (topic, message) {
            // console.log("MESSAGE ARRIVED: "+ message + "from topic: "+ topic)
            if (topic == vm.topic) {
                vm.value = message
                vm.$forceUpdate
            }
        })
    }
  }

</script>