<template>
<v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app color="#EFEEF3">

        <v-list-item>
            <v-list-item-content class="ht">
                <v-img v-if="mini" src="/images/logo.png" max-height="20" max-width="20"></v-img>

                <v-row>
                    <v-col md="3" v-if="!mini">
                        <v-avatar max-height="45">
                            <img src="/images/logo.png">
                        </v-avatar>
                    </v-col>
                    <v-col cols="9" v-if="!mini">
                        <v-list-item-title class="title">
                            eStock
                        </v-list-item-title>
                        <v-list-item-subtitle>
                            For managing inventory
                        </v-list-item-subtitle>
                    </v-col>
                </v-row>
            </v-list-item-content>
        </v-list-item>

        <v-divider class="mt-0"></v-divider>

        <v-list class="red_list" dense rounded>
            <v-list-item-group color="red">
                <v-list-item v-for="item in items" :key="item.title" link :to="item.action" class="nav-link">
                    <v-list-item-icon v-bind="attrs" v-on="on">
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title v-bind="attrs" v-on="on">
                        {{ item.title }}
                    </v-list-item-title>
                </v-list-item>
            </v-list-item-group>
        </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="white" style="box-shadow: rgb(0 0 0 / 7%) 0px 1px 50px 0px" height="69">
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

        <v-toolbar-title>Dashboard</v-toolbar-title>
    </v-app-bar>

    <v-main style="background: #F5F5F5">
        <v-container>
            <v-row>
                <v-col cols="12" md="8">
                    <v-img src="/images/im.png" height="223px" style="box-shadow: rgb(0 0 0 / 7%) 0px 1px 50px 0px; border-radius: 10px 10px 10px 10px">
                        <h4 style="margin-left: 40px; margin-top: 50px;font-weight: 200;margin-bottom:0px;">Welcome to</h4>
                        <h2 style="margin-top: 50px;margin-left: 40px;margin-top:0px;color:#bfbfbf;">eSchool System</h2>
                    </v-img>
                </v-col>
                <v-col md="2" cols="12">
                    <v-card color="red" style="height:223px; box-shadow: rgb(0 0 0 / 7%) 0px 1px 50px 0px; ">
                        <v-icon style="font-size: 150px;opacity:0.4;" x-large color="">mdi-rocket-launch</v-icon>
                        <v-card-text style="margin-top: -30px; text-align:center;color:white">
                            Waiting order
                            <h2>
                            03
                            </h2>
                        </v-card-text>
                    </v-card>
                </v-col>
                <v-col md="2" cols="12">
                    <v-card style="box-shadow: rgb(0 0 0 / 7%) 0px 1px 50px 0px; ">
                        <v-card-title>test</v-card-title>
                    </v-card>
                </v-col>

            </v-row>
        </v-container>
    </v-main>
</v-app>
</template>

<script>
export default {
    data: () => ({
        drawer: null,
        items: [{
                icon: "mdi-view-dashboard",
                title: "Dashboard",
                action: "/",
            },
            {
                icon: "mdi-bell-ring",
                title: "Dashboard1",
                action: "/1",
            },
        ]
    }),
}
</script>

<style scoped>
.red_list .v-list-item-group .v-list-item--active {
    background-color: #DC1A22;
    color: white;
}
</style>
