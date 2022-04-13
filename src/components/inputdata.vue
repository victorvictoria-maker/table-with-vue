<template>
    <div>
        <input v-model="nameinput" placeholder="name" type="text" id="">
        <input v-model="schoolinput" placeholder="school" type="text" id="">
        <input v-model="deptinput" placeholder="department" type="text" id="">
        <button v-on:click="getData()">Click Me</button>
    </div>
</template>

<script>
export default {
    name: "Inputdata",
    data() {
        return {
            nameinput: "",
            schoolinput: "",
            deptinput: ""
        }
    },
    methods: {
        getData() {
            if ((this.nameinput != "") && (this.schoolinput != "") && (this.deptinput != "")) {
                 this.$emit('taketoapp', this.nameinput, this.schoolinput, this.deptinput);
            } else {
                alert ("Put necessary information!");
            }
        }
    }
    
}
</script>

<style scoped>

</style>