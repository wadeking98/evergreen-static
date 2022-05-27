<template>
    <div>
        <v-footer app bottom fixed padless>
            <v-card flat tile width="100%">
                <v-card-text class="text-center">
                    {{ new Date().getFullYear() }} — <strong>Evergreen Art</strong>
                </v-card-text>
                <v-card-text class="pt-0 text-center">
                    <strong>Contact us: <v-btn icon v-for="item in contactItems" :key="item.icon"> <a class="contact-link" :href="item.link">
                                <v-icon>{{ item.icon }}</v-icon>
                            </a></v-btn></strong>
                </v-card-text>
            </v-card>
        </v-footer>
    </div>
</template>

<script>
export default {
    name: 'AppFooter',
    data: () => ({
        drawer: false,
        group: null,
        contactItems: [
            { icon: "mdi-instagram", link: "https://www.instagram.com/evergreens.art/" },
            { icon: "mdi-mail", link: "mailto:rose@heronweb.ca" },
            { icon: "mdi-phone", link: "tel:778-677-7706" }
        ]
    }),
}
</script>
<style>
.contact-link{
    text-decoration: none;
}
</style>
