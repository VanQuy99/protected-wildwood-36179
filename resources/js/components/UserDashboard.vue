<template>
    <div class="user-dashboard">
        <div class="list-user-comp">
            <h4>LIST USER</h4>
<!--            dataUserChildren để hứng dữ liệu từ thằng con là hàm userSelected (2)-->
            <ListUser @userSelected="dataUserChildren"></ListUser>
        </div>
        <div class="user-detail-comp">
            <h4>USER DETAIL</h4>
<!--            gán dữ liệu thằng cha cho thằng con mới (4)-->
<!--            Dữ liệu truyền qua cho thằng con phải là object-->
            <UserDetail :userDetailInfo="responseUserChildren"></UserDetail>
        </div>

        <div class="binding-html-comp">
            <h4>BINDING HTML</h4>
            <BindingHTML></BindingHTML>
        </div>
    </div>
</template>

<script>
    import ListUser from './ListUser'
    import UserDetail from './UserDetail'
    import BindingHTML from './BindingHTML'

    export default {
        components: {
            ListUser,
            UserDetail,
            BindingHTML
        },
        data() {
            return {
                responseUserChildren: {}
            }
        },
        methods: {
            dataUserChildren(user) {
                console.log(user)
                //gán dữ liệu cho thằng cha (3)
                this.responseUserChildren = user
            }
        }

    }
</script>