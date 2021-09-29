<template>
    <div>
        <router-view v-if="loadedConfig" :key="$route.fullPath"></router-view>
        <template v-else>
            <div class="container mt-5">
                <div v-if="loadedConfig===false" class="box has-text-centered">
                    <Busy>
                        <br>
                        <strong>Loading configurations</strong>
                    </Busy>
                </div>
                <div v-else-if="loadedConfig===null" class="alert alert-danger" role="alert">
                    <strong>Error:</strong> Failed to load configurations from server.
                </div>
            </div>
        </template>
        
    </div>
</template>

<script>
    export default {
        data() {
            return {
                loadedConfig: false
            }
        },

        mounted() {
            // load config from server.
            this.getConfigurations();
        },

        methods: {
            getConfigurations() {
                return this.$api.getFromRoute('/data/config', {}, {
                    yes: ({config}) => {
                        if (config) this.$store.commit('setConfig', config);
                        this.loadedConfig = true;
                    }
                })
            }
        }
    }
</script>
