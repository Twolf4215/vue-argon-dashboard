<template>
    <div >
        <p class="text-light p-3 bg-danger bg-opacity-10 border border-info border-start-0 rounded-end">Apakah Anda yakin ingin menghapus ini ?</p>
        <button class="btn btn-danger" @click="deleteUser()">Delete</button>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    methods: {
        async deleteUser() {
            let x = window.confirm("You want to delete the user?");
            if (x) {
                const user = await axios.delete(
                    "https://reqres.in/api/users/2"
                );
                console.log(user);
                alert("User deleted!");
            }
        },
    },
}
</script>