<template>
    <ul>
        <li :class="{ active: modelValue === 'bad' }">
        <button type="button" @click="activate('bad')">Bad</button>
        </li>
        <li :class="{ active: modelValue === 'poor' }">
            <button type="button" @click="activate('poor')">Poor</button>
        </li>
        <li :class="{ active: modelValue === 'average' }">
            <button type="button" @click="activate('average')">Average</button>
        </li>
        <li :class="{ active: modelValue === 'good' }">
            <button type="button" @click="activate('good')">Good</button>
        </li>
        <li :class="{ active: modelValue === 'great' }">
            <button type="button" @click="activate('great')">Great</button>
        </li>
    </ul>
</template>

<script>
export default {
    props: ['modelValue'],
    emit: ['update:ModelValue'],
    //   data() { include in computed so rating resets
    //     return {
    //       activeOption: null,
    //     };
    //   },
    // computed: { skip and change activeOption to modelValue
    //     activeOption() {
    //         return this.modelValue;
    //     }
    // },
    methods: {
        activate(option) {
            this.activeOption = option;
            this.$emit('update:modelValue', option);
        },
    },
};
</script>

<style scoped>
.active {
    border-color: purple;
}

.active button {
    color: purple;
    background-color: rgb(218, 176, 226);
}

ul {
    list-style: none;
    margin: 0.5rem 0;
    padding: 0;
    display: flex;
}

li {
    margin: 0 0rem;
    border: 1px solid #ccc;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

button {
    font: inherit;
    border: none;
    background-color: transparent;
    cursor: pointer;
    padding: 1.5rem;
    margin: 0;
}

ul {
    list-style: none;
    margin: 0.5rem 0;
    padding: 0;
    display: flex;
}

li {
    margin: 0 0.5em;
    border: 1px solid #ccc;
    padding: 0rem;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
