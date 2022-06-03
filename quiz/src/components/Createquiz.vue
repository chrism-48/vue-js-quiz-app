<template>
    <div class="ui basic content center aligned segment">
        <button class="ui basic button icon" v-show="!iscreating" v-on:click="openForm">
            <i class="plus icon"></i>
        </button>

        <div class="ui centered card" v-show="isCreating">
            <div class="content">
                <div class="ui form">
                    <div class="field">
                        <label>Title</label>
                        <input v-model="titleText" type="text">
                    </div>
                    <div class="field">
                        <label>Description</label>
                        <input v-model="descriptionText" type="text">
                    </div>
                    <div class="ui two button attahed buttons">
                        <button class="ui basic green button" v-on:click="saveList">Save</button>
                        <button class="ui basic red button" v-on:click="closeForm">Cancel</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>






<script>
export default {
    data() {
        return {
            isCreating: false,
            titleText: "",
            descriptionText: "",
        }
    }, 
    methods: {
        openForm() {
            this.isCreating = true;
        },
        closeForm() {
            this.isCreating = false;
        },
        saveList() {
            console.log(`Title Text: ${this.titleText}`);
            console.log(`Description Text: ${this.descriptionText}`)
        }
    }
}
</script>






<style>

</style>