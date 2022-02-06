<template>
    <base-card>
    <base-button @click="setSelectedTab('stored-resources')">Stored Resources</base-button>
    <base-button @click="setSelectedTab('add-resources')">Add Resources</base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>
 

<script>
import StoredResources from "./StoredResources.vue";
import AddResource from "./AddResource.vue";

export default {
    components: {
        StoredResources,
        AddResource
    },
    data() {
        return {
            selectedTab: 'stored-resources',
            storedResources: [
            { 
                id: 'official-guide',
                title: 'Alphabet Stock Is Soaring After an Impressive Earnings Beat',
                description: 'The Google parent reported fourth-quarter sales of $75.3 billion, up 32% year over year. The company also announced a 20-for-one stock split.',
                link: 'vuejs.org'
            },
            { 
                id: 'google',
                title: 'A Normal Supply Chain? It’s ‘Unlikely’ in 2022',
                description: 'The chaos at ports, warehouses and retailers will probably persist through the year, and perhaps even longer.',
                link: 'google.org'
            },
          ],
        };
    },provide() {
        return {
            resources: this.storedResources
        };
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        }
    }
}
</script>
