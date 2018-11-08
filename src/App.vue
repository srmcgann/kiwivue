<template>
    <div id="app">
        <KiwiIrc :kiwi-config="kiwiConfig" :kiwi-path="kiwiPath"/>
    </div>
</template>

<script>
import KiwiIrc from 'kiwiirc/Kiwi.vue'

export default {
    components: {
        KiwiIrc
    },
    data() {
        return {
            kiwiPath: '../node_modules/kiwiirc/dist/',
            kiwiConfig: {
                    "windowTitle": "Kiwi IRC - The web IRC client",
                    "startupScreen": "welcome",
                    "kiwiServer": "https://cantelope.ml:8110/webirc/kiwiirc/",
                    "restricted": false,
                    "theme": "Nightswatch",
                    "themes": [
                        { "name": "Default", "url": "static/themes/default" },
                        { "name": "Dark", "url": "static/themes/dark" },
                        { "name": "Coffee", "url": "static/themes/coffee" },
                        { "name": "GrayFox", "url": "static/themes/grayfox" },
                        { "name": "Nightswatch", "url": "static/themes/nightswatch" },
                        { "name": "Osprey", "url": "static/themes/osprey" },
                        { "name": "Radioactive", "url": "static/themes/radioactive" },
                        { "name": "Sky", "url": "static/themes/sky" }
                    ],
                    "startupOptions" : {
                        "server": "irc.freenode.net",
                        "port": 6667,
                        "tls": false,
                        "direct": false,
                        "channel": "#hohoho",
                        "nick": "kiwi-n?",
                        "autoConnect": true,
                        "state_key": false
                    },
                    "embedly": {
                        "key": ""
                    },
                    "plugins": [
                    ]
                }

        }
    }
}
</script>

<style scoped>
#app {
    margin-left: auto;
    margin-right: auto;
    margin-top: 12.5vh;
    height: 75vh;
    width: 75%;
    border: 1px solid black;
}
</style>
