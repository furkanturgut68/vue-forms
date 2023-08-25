 <template>
    <ul>
        <li :class="{activated: modelValue === 'poor'}"><button @click="activated('poor')" type="button">Poor</button></li>
        <li :class="{activated: modelValue === 'average'}"><button @click="activated('average')" type="button">Average</button></li>
        <li :class="{activated: modelValue === 'great'}"><button @click="activated('great')" type="button">Great</button></li>

    </ul>    
 </template>

 <script>
export default {
    props : ['modelValue'],
    emits: ['update:modelValue'],
   
   
    methods: {
        activated(option){
            this.$emit('update:modelValue',option);
           
        }
    }
}
</script>

<style>
.activated {
    border-color: #a00078;
}
.activated button {
    color: #a00078;
}

ul {
    display: flex;
    list-style: none;
    margin:  0.5rem 0;
    padding: 0;
}

li {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 1rem;
    border: 1px solid #ccc;
    margin: 0 1rem;
}

button {
    font: inherit;
    cursor: pointer;
    border: none;
    background-color: transparent;
}
</style>