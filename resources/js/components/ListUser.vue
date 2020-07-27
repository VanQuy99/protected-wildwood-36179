<template>
    <div class="list-user">
        <table>
            <thead>
                <th>Name</th>
                <th>Location</th>
                <th>DOB</th>
            </thead>
            <tbody>
                <tr v-for="user in listUser">
<!--                    set user vào trong hàm seletedUser để đưa ra cho thằng Cha (1)-->
                    <td><a @click="selectedUser(user)">{{ user.name.title }} - {{ user.name.first }}</a></td>
                    <td>{{ user.location.city }}</td>
                    <td>{{ user.dob.date }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    import data from './data.json'

    export default {
        data() {
            return {
                listUser: data
            }
        },
        methods: {
            selectedUser(user) {
                //hàm emit để lưu lại
                this.$emit('userSelected', user)
            }
        }

    }
</script>