<template>
    <div class="select-area">
        <select @change="$emit('changeValue', selectValue)" v-model="selectValue" name="" id="">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
            <option value="r/b">R&B</option>
        </select>
        <div class="select-text">Risultato:</div>
    </div>
</template>

<script>
export default {
    name: 'Select',
    data: function(){
        return {
            selectValue: ''
        }
    },
}
</script>

<style scoped lang="scss">
@import '../style/generals.scss';

.select-area{
    background-color: $brand-secondary-color;

    select{
        padding: 5px 20px;
        margin: 40px;
        font-size: 20px;
        color: white;
        background-color: $brand-primary-color;
        border: 1px solid white;
        border-radius: 10px;
    }

    .select-text{
        margin-left: 40px;
        color: white;
        font-size: 20px;
    }
}
</style>