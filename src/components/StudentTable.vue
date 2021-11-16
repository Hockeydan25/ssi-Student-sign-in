<template>
    <div>
        <div class="card student-list m-2 p-2"> <!--start card studentlist Div container-->
            <h4 class="card-title">Student List</h4>
            <div id="student-table"> <!--start student-table Div container-->
                <table class="table"> <!--table created-->
                    <tr> 
                        <th>Name</th> <!-- table headers title for each row-->
                        <th>StarID</th>
                        <th>Present?</th>
                    </tr>
                   <!--  created table rows 
                   Each row will have a checkbox, bound to the app's data 
                   When the checkbox is checked/unchecked, the student will be signed in/out -->
                    <tr v-for="student in students" v-bind:class="{ present:student.present, absent: !student.present }"> <!--variable student is created here -->
                        <td>{{student.name}}</td>
                        <td>{{student.starID}}</td>
                        <td>
                            <input type="checkbox" v-model="student.present" v-on:change="arrivedOrLeft(student)"> <!--check box for a present student.-->
                        </td>
                    </tr>
                </table>
            </div> <!--end student-table Div container-->
        </div> <!--end card student-listDiv container-->

    </div>
</template>

<script>
export default {
    name: 'StudentTable',
    props: {
        students: Array
    },
    methods: {
        arrivedOrLeft(){
            //TODO emit message to parent.
        }
    }
}
</script>

<style scoped>

</style>