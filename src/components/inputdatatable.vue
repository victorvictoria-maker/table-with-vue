<template>
    <div>
        <table>
            <tr>
                <th>S/N</th>
                <th>Name</th>
                <th>School</th>
                <th>Department</th>
            </tr>
         <!-- for loop to run the table with the array -->
         <tr v-bind:key="i" v-for="(studentinfo, i) in getarray">
             <td>{{i+1}}</td>
            <td>{{studentinfo.stuname}}</td>
            <td>{{studentinfo.stuschool}}</td>
            <td>{{studentinfo.studept}}</td>
            <td>
                <button>Edit</button>
            </td>
             <td>
                <button v-on:click="$emit('delTable', i)"> Delete</button>
            </td>
        </tr> 
         </table>  
    </div>
</template>

<script>

export default {
    name: "Inputdatatable",

    props: ["getarray"],

    data() {
        return {
        }
    }
}
</script>

<style scoped>

</style>