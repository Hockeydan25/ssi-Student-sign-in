<template><!-- template/HTML here -->
    <div><!--Start Main DIV -->
        <!--  show a message when student arrives or leaves  -->
        <div v-if="student.name">

            <div class="alert alert-primary" v-if="student.present">
                Welcome, {{ student.name }}
            </div>

            <div class="alert alert-secondary" v-else>
                Goodbye, {{ student.name }}. See you later!
            </div>

        </div>    

    </div><!--END Main DIV -->
</template>

<script>
export default {
    name: 'StudentMessage',
    props: {
       student: Object 
    }
   
}
</script>

<style scoped>

</style>