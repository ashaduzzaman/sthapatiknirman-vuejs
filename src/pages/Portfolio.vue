<template>
    <v-container fluid>
                    <v-flex text-center>
                        <!-- <div class="section-subtitle title">Our Works</div> -->
                        <h4 class="section-title">Categories</h4>
                        <div class="theme-separator-line-horrizontal-full"></div>
                    </v-flex>
                    <!-- <div class="title" style="background-color: #C2932D; padding:5px; border-radius: 5px; text-align: center;">{{ project_category.name }}</div> -->
                    <v-row class="mt-5 ml-10 mr-10">
                        <v-col v-for="project_category in categorywise_data" :key="project_category.id">
                            <v-hover v-slot:default="{ hover }">
                                <v-card elevation="12" class="mx-auto" max-width="344" color="blue" @click.native="getProjects(project_category.id)">
                                    <v-img height="280" :src="image_base_url+project_category.image_path">
                                        <v-expand-transition>
                                            <div
                                                v-if="hover"
                                                class="d-flex transition-fast-in-fast-out orange darken-2 v-card--reveal display-3 white--text"
                                                style="height: 100%;"
                                            >
                                                {{ project_category.name }}
                                            </div>
                                        </v-expand-transition>
                                    </v-img>
                                </v-card>
                            </v-hover>
                        </v-col>
                    </v-row>
        </v-container>
</template>

<script>
    export default {
        data: () => ({
            categorywise_data: "",
            image_base_url: ""
        }),
        async created(){
            this.progressbar = true;
            await this.axios.get(process.env.VUE_APP_API_URL+'/project-category').then((response)=> {
                console.log(response.data);
                this.categorywise_data = response.data;
            });
            this.image_base_url = process.env.VUE_APP_IMG_URL;
        },

        methods:{
            getProjects(categoryId){
                console.log(categoryId);
                this.$router.push({ path: `/projects/${categoryId}` })
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>