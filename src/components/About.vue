<template>
    <v-row align="left" justify="left">
        <v-flex xs12 sm5 md6 lg8 just>
            <v-container>
                <v-row align="left" justify="left">
                    <div :class="{'display-3 font-weight-bold ': $vuetify.breakpoint.smAndUp, 'display-2 font-weight-bold': $vuetify.breakpoint.smAndDown}">
                        Who We Are
                    </div>
                    <div :class="{'subtitle-1': $vuetify.breakpoint.smAndDown}" style="opacity: 0.75; margin-top:10px;">
                        LiQuid Gaming was created back in May of 2019 by our founding fathers. Since then we have grown to upward of 2000 members in our Discord and over 380 LiQ members.
                        Our board of directors currently consist of the 17 members below, not listed are our many trustworthy admins for our various servers. If you have any questions or
                        inquiries, please contact us in our Discord.
                    </div>
                    <v-container class="my-5">
                        <v-layout row wrap>
                            <v-flex xs12 sm6 md4 lg3  v-for="(person, index) in teamMembers" :key="index">
                                <v-hover v-slot:default="{ hover }">
                                    <v-card class="text-xs-center ma-3" :elevation="hover ? 10 : 2">
                                        
                                    </v-card>
                                </v-hover>
                            </v-flex>
                        </v-layout>
                    </v-container>
                </v-row>
            </v-container>
        </v-flex>        
        
        <v-spacer></v-spacer>
        <template>
            <v-flex xs12 sm7 md6 lg4 xl3 just>
                <v-hover v-slot:default="{ hover }">
                    <v-card :elevation="hover ? 10 : 5" style="border-radius: 20px;">
                        <!-- <v-card-text>
                            <v-layout wrap my-5 style="margin: 0 !important;">
                                <v-flex justify-center class="mt-2">
                                    <v-layout wrap>
                                        <div>
                                            <div :class="{'display-1 font-weight-bold ': $vuetify.breakpoint.smAndUp}">
                                                Join Our Discord
                                            </div>
                                            <div v-if="$vuetify.breakpoint.smAndDown">
                                                <iframe src="https://discordapp.com/widget?id=583882225012047873&theme=dark" width="275" height="400" allowtransparency="true" frameborder="0" sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"></iframe>
                                            </div>
                                            <div v-else>
                                                <iframe src="https://discordapp.com/widget?id=583882225012047873&theme=dark" width="350" height="400" allowtransparency="true" frameborder="0" sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"></iframe>
                                            </div>
                                        </div>
                                    </v-layout>
                                </v-flex>
                            </v-layout>
                        </v-card-text>
                            <div>
                                <v-expansion-panels>
                                    <v-expansion-panel>
                                        <v-expansion-panel-header class="titleColour">Rules</v-expansion-panel-header>
                                        <v-expansion-panel-content>
                                            <template v-slot:actions>
                                                <v-icon color="primary">gavel</v-icon>
                                            </template>
                                            <v-flex v-for="(rule, index) in discord.rules" :key="index">
                                                <v-card class="card-container" style="margin:7px;background:#262626;">
                                                    <v-card-text class="px-4">
                                                        <v-card-title>
                                                            <h5 class="titleColour">{{index+1}}: {{rule.title}}</h5>
                                                        </v-card-title>
                                                        <v-card-subtitle v-if="rule.description != null">
                                                            <p>{{rule.description}}</p>
                                                        </v-card-subtitle>
                                                    </v-card-text>
                                                </v-card>
                                            </v-flex>
                                        </v-expansion-panel-content>
                                    </v-expansion-panel>
                                </v-expansion-panels>
                            </div> -->
                    </v-card>  
                </v-hover>
            </v-flex>
        </template>
    </v-row>
</template>

<script>
export default {

};
</script>

<style lang="scss" scoped>

.v-card__text, .v-card__title {
  word-break: normal !important;
}
.preWrapped{
  white-space: pre-wrap;
}
.flex.xl3{
    flex-basis: 20% !important;
}
</style>
