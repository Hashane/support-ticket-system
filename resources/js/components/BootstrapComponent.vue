<template>
    <div class="container">
        <div class="row justify-content-center">
            <div>
                <div class="add-item-form">
                    <h1>{{ header }}</h1>
                    <input
                        type="text"
                        v-model="newItem"
                        v-on:keyup.enter="saveItem"
                    />
                    <button
                        class="btn btn-primary"
                        v-on:click="saveItem"
                        v-bind:disabled="newItem.length === 0"
                    >
                        Save
                    </button>
                </div>
                <p v-if="items.length === 0">No Items!</p>
                <ul>
                    <li v-for="item in items">{{ item }}</li>
                </ul>
            </div>
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>
                    <div class="card-body">I'm an example component.</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            header: "Damn!",
            newItem: "",
            items: ["yoyo", "yeye", "zzzz"],
        };
    },
    methods: {
        saveItem: function () {
            this.items.push(this.newItem);
            this.newItem = "";
        },
    },
    mounted() {
        console.log("Component mounted.");
    },
};
</script>
