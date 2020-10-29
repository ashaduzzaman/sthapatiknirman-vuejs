<template>
    <v-container>
        <v-layout class="pa-5">
            <v-flex text-center>
                <!-- <div class="section-subtitle title">Our Works</div> -->
                <h4 class="section-title">Projects</h4>
                <div class="theme-separator-line-horrizontal-full"></div>
            </v-flex>
        </v-layout>
        <v-container fluid>
            <v-row>
                <v-col>
                    <v-row class="mt-5">
                        <v-col v-for="item in projects" :key="item.id">
                            <v-hover v-slot:default="{ hover }">
                                <v-card elevation="12" class="mx-auto" max-width="344" color="blue" @click.native="OpenDialogBox(item)">
                                    <v-img height="280" :src="image_base_url+item.thumbnail_image">
                                        <v-expand-transition>
                                            <div
                                                v-if="hover"
                                                class="d-flex transition-fast-in-fast-out orange darken-2 v-card--reveal display-3 white--text"
                                                style="height: 100%;"
                                            >
                                                {{ item.name }}
                                            </div>
                                        </v-expand-transition>
                                    </v-img>
                                </v-card>
                            </v-hover>
                        </v-col>
                    </v-row>
                </v-col>
            </v-row>
        </v-container>
        <v-dialog
        v-model="dialog"
        full-screen
        transition="dialog-bottom-transition"
        >
            <v-card color="transparent" class="ma-0 pa-0">
            
                <div style="background-color: white;">
                    <v-img
                    :src="image_base_url+detailsModal.thumbnail_image"
                    height="500px"
                    >
                        <div class="l-section-overlay"></div>
                        <div class="centered" style="color:white;">{{ detailsModal.name }}</div>
                        <v-row>
                            <v-col class="text-right">
                                <v-btn
                                icon
                                x-large
                                @click="dialog = false;"
                                color="black"
                                class="text-right"
                                >
                                    <v-icon>mdi-close-thick</v-icon>
                                </v-btn>
                            </v-col>
                        </v-row>
                    </v-img>
                    <v-card-text>
                        <v-container>
                            <v-layout>
                                <v-row>
                                    <v-col>
                                        <h2 class="ma-4">Project Details</h2>
                                        <p class="ma-4">
                                            {{ detailsModal.description }}
                                        </p>
                                    </v-col>
                                    <v-col>
                                        <v-list>
                                            <v-list-item three-line>
                                                <v-list-item-icon>
                                                    <v-icon>mdi-account</v-icon>
                                                </v-list-item-icon>
                                                <v-list-item-content>
                                                    <v-list-item-title>Main Architect</v-list-item-title>
                                                    <v-list-item-subtitle>
                                                    {{ detailsModal.main_architect }}
                                                    </v-list-item-subtitle>
                                                </v-list-item-content>
                                            </v-list-item>
                                        </v-list>
                                        <v-list class="team_members_title">
                                            <v-list-item>
                                                <v-list-item-icon>
                                                    <v-icon>mdi-account</v-icon>
                                                </v-list-item-icon>
                                                <v-list-item-content>
                                                    <v-list-item-title>Team Members</v-list-item-title>
                                                </v-list-item-content>
                                            </v-list-item>
                                        </v-list>
                                        <v-list class="team_members">
                                            <v-list-item
                                            v-for="(item, i) in detailsModal.team_members"
                                            :key="i"
                                            >
                                                <v-list-item-icon>
                                                    <v-icon></v-icon>
                                                </v-list-item-icon>
                                                <v-list-item-content class="team_members_content">
                                                    <v-list-item-subtitle>
                                                        {{ item }}
                                                    </v-list-item-subtitle>
                                                </v-list-item-content>
                                            </v-list-item>
                                        </v-list>
                                    </v-col>
                                </v-row>
                            </v-layout>
                            <div>
                                <h2 class="mb-5">Project Images</h2>
                                <v-row>
                                    <v-col v-for="image in detailsModal.photos" :key="image.id">
                                        <v-img width="350" height="350" :src="image_base_url+image.image_path" alt="images" @click="getId(image)"></v-img>
                                    </v-col>
                                </v-row>
                            </div>
                        </v-container>
                    </v-card-text>
                </div>
            </v-card>
        </v-dialog>
        <v-dialog v-model="dialogImage" max-width="800px">
            <v-card color="transparent" width="800px" height="800px">
                <v-img :src="singleImage" width="800px" height="800px">
                    <v-row>
                        <v-col class="text-right">
                            <v-btn
                            icon
                            x-large
                            @click="dialogImage = false;"
                            color="black"
                            >
                                <v-icon>mdi-close-thick</v-icon>
                            </v-btn>
                        </v-col>
                    </v-row>
                </v-img>
            </v-card>
        </v-dialog>
    </v-container>
</template>

<script>
    export default {
        data: () => ({
            dialog: false,
            dialogImage: false,
            detailsModal : "",
            singleImage: "",
            projects: "",
            image_base_url: ""
        }),
        async created(){
            // this.progressbar = true;
            console.log(this.$route.params.id);
                await this.axios.get(process.env.VUE_APP_API_URL+'/project-category/'+this.$route.params.id).then((response)=> {
                    console.log(response.data);
                    this.projects = response.data;
                });
            this.image_base_url = process.env.VUE_APP_IMG_URL;
        },
        methods: {
        OpenDialogBox(item){
            console.log(item);
            this.detailsModal = item;
            this.dialog = true;
        },
        getId(image){
            console.log(image)
            this.singleImage = this.image_base_url+image.image_path
            this.dialogImage = true
        }
    }
    }
</script>

<style lang="scss" scoped>

</style>