<template>
    <div class="ui basic content center aligned segment">
        <button id="plusbutton" class="ui basic button icon" v-show="!iscreating" v-on:click="openForm">
            <i class="plus icon"></i>
        </button>

        <div class="ui centered card" v-show="isCreating">
            <div class="content">
                <div class="ui form">
                    <div class="field">
                        <label>Title</label>
                        <input class="inputs" v-model="titleText" type="text" placeholder="title...">
                    </div>
                    <div class="field">
                        <label>Description</label>
                        <input class="inputs" v-model="descriptionText" type="text" placeholder="description...">
                    </div>
                    <!-- <div class="ui two button attached buttons"> -->
                        <div class="ui two buttons" ></div>
                        <button class="ui basic button" v-on:click="saveQuiz">Save</button>
                        <button class="ui basic button" v-on:click="closeForm">Cancel</button>
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
        saveQuiz() {
            this.$emit('createquiz', {
                title: this.titleText,
                description: this.descriptionText,
            });
            this.titleText =  '';
            this.descriptionText = '';
            this.isCreating = false;
        }
    }
}
</script>






<style>
body {
    background-color:rgb(255, 255, 255);
}
.ui.basic.button {
    width:85px;
    border-style:solid;
    border-width:.01px;
    box-shadow:2px 2px 2px rgba(0, 0, 0, 0.308);
}
.ui.basic.button:hover {
    border-width:1.5px;
    box-shadow:2px 2px 2px rgba(0, 0, 0, 0.308);   
}

#plusbutton {
    border-width:.01px;
    box-shadow:2px 2px 8px rgba(0, 0, 0, 0.418);
}   

</style>