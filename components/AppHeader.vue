<template>
    <div>
        <v-app-bar fixed elevation="0">
            <v-img :src="require('../assets/logo.png')" contain class="mx-2" height="50px" max-width="50px" />

            <v-app-bar-title class="ml-2">
                <div>Evergreen Art</div>
            </v-app-bar-title>

            <v-spacer></v-spacer>

            <v-app-bar-nav-icon v-if="$vuetify.breakpoint.mdAndDown" @click="drawer = true"></v-app-bar-nav-icon>
            <v-tabs right v-else>
                <v-tab v-for="item in navItems" :key="item.title" @click="itemClickHandler(item.link)">
                    {{ item.title }}
                </v-tab>
                <v-switch v-model="$vuetify.theme.dark" @change="switchHandler"
                    :label="`${$vuetify.theme.dark ? 'DARK' : 'LIGHT'} MODE`" class="mt-5 mr-4"></v-switch>
            </v-tabs>
        </v-app-bar>
        <v-navigation-drawer fixed v-if="$vuetify.breakpoint.mdAndDown && drawer" v-model="drawer" right temporary>
            <v-list nav dense class="mt-12">
                <v-list-item-group v-model="group">
                    <v-list-item v-for="item in navItems" :key="item.title" @click="itemClickHandler(item.link)">
                        <v-list-item-icon>
                            <v-icon>{{ item.icon }}</v-icon>
                        </v-list-item-icon>
                        <v-list-item-title>{{ item.title }}</v-list-item-title>
                    </v-list-item>

                </v-list-item-group>
            </v-list>
            <v-spacer></v-spacer>
            <v-switch v-model="$vuetify.theme.dark" @change="switchHandler"
                :label="`${$vuetify.theme.dark ? 'Dark' : 'Light'} Mode`" class="mt-15 ml-5"></v-switch>
        </v-navigation-drawer>
    </div>
</template>

<script>

export default {
    name: 'AppHeader',

    data: () => ({
        drawer: false,
        group: null,
        navItems: [
            { icon: "mdi-home", title: "Home", link: "/" },
            { icon: "mdi-palette", title: "Paintings", link: "/paintings" },
            { icon: "mdi-format-paint", title: "Murals", link: "/murals" },
            { icon: "mdi-pen", title: "Digital Art", link: "/digital" },
            { icon: "mdi-fountain-pen", title: "Tattoo Design", link: "/tattoo" },
            { icon: "mdi-pencil-ruler", title: "Commission", link: "/commission" }

        ]
    }),
    computed: {
        isDark() {
            return localStorage.dark
        }
    },

    methods: {
        itemClickHandler(link) {
            this.drawer = false
            this.$router.push(link)
        },
        switchHandler() {
            localStorage.dark = this.$vuetify.theme.dark
        }
    },
    beforeMount() {
        //if localstorage has a dark/light preference
        if (localStorage.dark !== undefined) {
            this.$vuetify.theme.dark = localStorage.dark === "true"
        } else {
            //check if browser supports dark mode.
            if (window.matchMedia && window.matchMedia('(prefers-color-scheme)').media !== 'not all') {
                //if user prefers light mode switch to light mode
                if (window.matchMedia('(prefers-color-scheme: light)').matches) {
                    this.$vuetify.theme.dark = false;
                }
            } else {
                console.log("got here")
                this.$vuetify.theme.dark = false;
            }
        }
    }
};
</script>