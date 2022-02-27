<template>
        <tr>
            <td>{{index + 1}}</td>
            <td>{{item}}</td>
            <td><button id="dltBtn" @click="accion">Eliminar</button></td>
        </tr>
</template>

<script>
export default {
    name: 'PaintList',
    data(){
        return{
            newArr: []
        }
    },
    props: {
        index: Number,
        item: String,
    },

    methods: {
        accion(){
            this.$emit('accion')
        }
    },
}
</script>

<style>

    #dltBtn {
        cursor: pointer;
        padding: 3px 5px;
        margin: auto 0;
        background-color: #3b3b3b;
        color: #fff;
        border-radius: 25px;
    }

    #dltBtn:hover{
        box-shadow: 0 0 5px red;
        color: #000;

    }

</style>