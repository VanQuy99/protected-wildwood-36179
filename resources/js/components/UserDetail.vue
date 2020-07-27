<template>
    <div class="user-detail" v-if="Object.keys(userDetailInfo).length !== 0">
        <div class="user-name">
            {{ userDetailInfo.name.first }}
        </div>
        <div class="user-location">
            {{ userDetailInfo.location.city }}
        </div>
        <div class="user-dob">
            {{ userDetailInfo.dob.date }}
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            userDetailInfo: {
                type: Object
            }
        }

    }
</script>