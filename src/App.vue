<template>
    <div id="app">
        <img src="./assets/logo.png">
        <KiwiIrc :config="config"/>
    </div>
</template>

<script>

window.kiwiConfig = function () {
    return        {
                    "windowTitle": "Kiwi IRC - The web IRC client",
                    "startupScreen": "welcome",
                    "kiwiServer": "https://localdev.clients.kiwiirc.com/webirc/kiwiirc/",
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
import KiwiIrc from 'kiwiirc/vue.js'

export default {
    name: 'App',
    components: {
        KiwiIrc
    },
    data() {
        return {
            config: window.kiwiConfig()
        }
    },
    mounted() {
        window.kiwiConfig = function () {
            return this.config
        }
    }
}
</script>

<style>
#app {
    margin-left: auto;
    margin-right: auto;
    margin-top: 25vh;
    height: 50vh;
    width: 50%;
    border: 1px solid black;
}
</style>
