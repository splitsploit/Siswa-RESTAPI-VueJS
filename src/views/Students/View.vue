<template>
    <div>
        <div class="card">
            <div class="card-header">
                <h4>
                    Students
                    <RouterLink to="/students/create" class="btn btn-primary float-end">
                        Add Student
                    </RouterLink>
                </h4>
            </div>
            <div class="card-body">
                <table class="table table-bordered">
                    <thead>
                        <th>ID</th>
                        <th>Name</th>
                        <th>Course</th>
                        <th>Phone</th>
                        <th>Created At</th>
                        <th>Action</th>             
                    </thead>
                    <tbody>
                        <td>1</td>
                        <td>Khusnul Yulandari</td>
                        <td>PHP</td>
                        <td>0831445212</td>
                        <td>10 March 2023</td>
                        <td>Action</td>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>

import axios from 'axios'

    export default {
        name: 'students',
        data() {
            return {
                students: []
            }
        },
        mounted() {
            this.getStudents();
        },
        methods: {
            getStudents() {
                axios.get('http://127.0.0.1:8000/api/students').then( res => {
                    console.log(res)
                } );
            }
        }
    }

</script>