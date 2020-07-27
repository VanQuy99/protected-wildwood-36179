<template>
    <div class="my-component">
        This is my component.
        {{reMessage}}
        <div>
            <button @click="sayHello">Click me</button>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                message: {
                    type: 'type',
                    text: 'text'
                }
            }
        },
        methods: {
            sayHello() {
                this.message.text = 'abc'
            }
        },
        computed: {
            reMessage() {
                return this.message.text.split('').reverse().join('')
            }
        },
        watch: {
            message: {
                handler: function() {
                    console.log('ok')
                },
                deep: true
            }
        }

    }
</script>

<style lang="scss" scoped>
    .my-component {
        color: blue;
    }
</style>