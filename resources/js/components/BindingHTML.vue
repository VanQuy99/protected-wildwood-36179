<template>
    <div class="binding-html">
        <div class="text-title" :class="{active: isActive}">
            This is text
        </div>
        <button @click="isActive = true">Active text</button>

        <div class="text">
            {{ message }}
        </div>

        <div class="input-form">
            <select v-model="message" name="" id="">
                <option disabled="">Choose</option>
                <option :value="values.one">ONE</option>
                <option :value="values.two">TWO</option>
            </select>
        </div>

        <div class="text">
            {{ inputMessage }}
        </div>
        <div class="input-form">
            <input type="text" :placeholder="placeholder" v-model.lazy="inputMessage">
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                isActive: false,
                message: '',
                inputMessage: '',
                values: {
                    one: 'day la one',
                    two: 'day la two'
                },
                placeholder: 'Input'
            }
        }
    }
</script>

<style lang="scss" scoped>
    .active {
        color: red;
    }
</style>