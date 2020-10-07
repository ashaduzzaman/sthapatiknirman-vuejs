<template>
    <v-container>
        <v-layout class="pa-10 mt-5">
            <v-flex text-center>
                <div class="section-subtitle title">Our Works</div>
                <h2 class="section-title"><b>Recent</b> Projects</h2>
                <div class="theme-separator-line-horrizontal-full"></div>
            </v-flex>
        </v-layout>
        <v-container fluid>
            <v-row class="mt-5 ml-10 mr-10">
                <v-col v-for="item in feedImages" :key="item.id">
                    <v-hover v-slot:default="{ hover }">
                        <v-card elevation="12" class="mx-auto" max-width="344" color="blue" @click.native="OpenDialogBox(item)">
                            <v-img height="280" :src="item.src">
                                <v-expand-transition>
                                    <div
                                        v-if="hover"
                                        class="d-flex transition-fast-in-fast-out orange darken-2 v-card--reveal display-3 white--text"
                                        style="height: 100%;"
                                    >
                                        {{ item.type }}
                                    </div>
                                </v-expand-transition>
                            </v-img>
                        </v-card>
                    </v-hover>
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
                    :src="detailsModal.src"
                    height="500px"
                    >
                        <div class="l-section-overlay"></div>
                        <div class="centered" style="color:white;">{{ detailsModal.title }}</div>
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
                                                    <v-list-item-title>Three-line item</v-list-item-title>
                                                    <v-list-item-subtitle>
                                                    Secondary line text Lorem ipsum dolor sit amet,
                                                    </v-list-item-subtitle>
                                                    <v-list-item-subtitle>
                                                    consectetur adipiscing elit.
                                                    </v-list-item-subtitle>
                                                </v-list-item-content>
                                            </v-list-item>
                                        </v-list>
                                        <v-list>
                                            <v-list-item three-line>
                                                <v-list-item-icon>
                                                    <v-icon>mdi-account</v-icon>
                                                </v-list-item-icon>
                                                <v-list-item-content>
                                                    <v-list-item-title>Three-line item</v-list-item-title>
                                                    <v-list-item-subtitle>
                                                    Secondary line text Lorem ipsum dolor sit amet,
                                                    </v-list-item-subtitle>
                                                    <v-list-item-subtitle>
                                                    consectetur adipiscing elit.
                                                    </v-list-item-subtitle>
                                                </v-list-item-content>
                                            </v-list-item>
                                        </v-list>
                                    </v-col>
                                </v-row>
                            </v-layout>
                            <div class="">
                                <h2 class="mb-5">Project Images</h2>
                                <v-row>
                                    <v-col v-for="(image, i) in galleryImages" :key="i">
                                        <v-img width="350" height="350" :src="image.urls.small" :alt="image.alt_description" @click="getId(image)"></v-img>
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
    components: {
    },
    data:() => ({
        feedImages: [
            {
                id: 1, 
                src:"https://images.unsplash.com/photo-1600745644600-20436d748941?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80", 
                title: "Vacation House",
                type: "Residential Building",
                description: "The two and half-storied ‘Vacation Villa’ in Himchori marine drive is a holiday destination amidst the natural setup of hills and sea. The existing topography inspired project is an alluring statement of contemporary architecture in Bangladesh. The purpose of the villa as a place of vacationing is well served as it ensemble two exquisite natural proponent of the site; sea and hills within its built premise. Knotting multiple forces of nature within a space to create and balance the desired psychological mood of relaxation for user was the challenge.",
            },
            {
                id: 2, 
                src:"https://images.unsplash.com/photo-1600748914826-67de972c3dca?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
                title: "Dane House",
                type: "Comercial Building",
                description: "The two and half-storied ‘Vacation Villa’ in Himchori marine drive is a holiday destination amidst the natural setup of hills and sea. The existing topography inspired project is an alluring statement of contemporary architecture in Bangladesh. The purpose of the villa as a place of vacationing is well served as it ensemble two exquisite natural proponent of the site; sea and hills within its built premise. Knotting multiple forces of nature within a space to create and balance the desired psychological mood of relaxation for user was the challenge."
            },
            {
                id: 3, 
                src:"https://images.unsplash.com/photo-1600497934937-2d02ebad5da3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80", 
                title:"Sky Castle",
                type: "Industrial Building",
                description: "The two and half-storied ‘Vacation Villa’ in Himchori marine drive is a holiday destination amidst the natural setup of hills and sea. The existing topography inspired project is an alluring statement of contemporary architecture in Bangladesh. The purpose of the villa as a place of vacationing is well served as it ensemble two exquisite natural proponent of the site; sea and hills within its built premise. Knotting multiple forces of nature within a space to create and balance the desired psychological mood of relaxation for user was the challenge."
            },
        ],
        dialog: false,
        dialogImage: false,
        detailsModal : "",
        singleImage: "",
        galleryImages: [],
        images: [
            {
                id: 1,
                project_id: 1,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo1.jpg"
                },
                alt_description: ""
            },
            {
                id: 2,
                project_id: 1,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo2.jpg"
                },
                alt_description: ""
            },
            {
                id: 3,
                project_id: 1,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo3.jpg"
                },
                alt_description: ""
            },
            {
                id: 4,
                project_id: 2,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo4.jpg"
                },
                alt_description: ""
            },
            {
                id: 5,
                project_id: 2,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo5.jpg"
                },
                alt_description: ""
            },
            {
                id: 6,
                project_id: 2,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo6.jpg"
                },
                alt_description: ""
            },
            {
                id: 7,
                project_id: 3,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo7.jpg"
                },
                alt_description: ""
            },
            {
                id: 8,
                project_id: 3,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo7.jpg"
                },
                alt_description: ""
            },
            {
                id: 9,
                project_id: 3,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo3.jpg"
                },
                alt_description: ""
            },
            {
                id: 10,
                project_id: 3,
                urls: {
                    small: "http://sthapotiknirman.com/assets/subuploads/Shaheen_Photo1.jpg"
                },
                alt_description: ""
            },
        ]
        
    }),
    methods: {
        OpenDialogBox(item){
            this.images.map((index) => {
                if(item.id == index.id){
                    this.galleryImages.push(index)
                }

            })
            this.detailsModal = item;
            this.dialog = true;
        },
        getId(image){
            this.singleImage = image.urls.small
            this.dialogImage = true
        }
    }
}
</script>

<style>
.v-card{
    cursor:pointer;
}

.l-section-overlay {
    position: absolute;
    background-color: rgba(0,0,0,0.3);
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}

.container { 
    width: 80vw; 
    margin: 0 auto; 
}

.button-wrapper { 
    display: flex; 
    justify-content: center; 
    margin-bottom: 25px; 
}

.btn { 
    font-size: 18px; 
    background-color: #42b983; 
    color: white; padding: 10px 20px;
}
</style>