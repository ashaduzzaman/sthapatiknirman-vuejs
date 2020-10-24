<template>
    <div>
        <v-parallax
            dark
            src="https://images.unsplash.com/photo-1596524430615-b46475ddff6e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
        >
            <v-row
                align="center"
                justify="center"
            >
                <v-col
                    class="text-center"
                    cols="12"
                >
                    <h1 class="display-1 font-weight-thin mb-4">
                        Contact Us
                    </h1>
                    <h4 class="subheading">
                        If you want to reach us
                    </h4>
                </v-col>
            </v-row>
        </v-parallax>
    </div>
</template>

<script>
    export default {
        data: () => ({

        }),
        
    }
</script>

<style scoped>
@media only screen and (min-width: 960px) {
    .v-parallax{
        height: 250px !important;
    }
}
@media only screen and (min-width: 1440px) {
    .v-parallax{
        height: 350px !important;
    }
}
@media only screen and (min-width: 2000px) {
    .v-parallax{
        height: 350px !important;
    }
}
</style>