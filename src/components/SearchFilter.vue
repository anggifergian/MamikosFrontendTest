<template>
    <input @input="onInput" @keypress.enter="onEnter" placeholder="Search name"
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-emerald-400" />
</template>

<script>
export default {
    emits: ['handleInputChange'],
    methods: {
        onInput(e) {
            this.$emit('handleInputChange', e.target.value)
        },
        onEnter(e) {
            console.log("Enter...", e.target.value)
        }
    }
}
</script>