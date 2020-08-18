<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Enter Article">
            <input type="text" v-model="quantity" name="quantity" placeholder="Enter Quantity">
            <input type="text" v-model="vendor" name="vendor" placeholder="Enter Vendor">
            <input type="submit" value="Submit" class="btnsubmit">
        </form>
    </div>
</template>


<script>
import {v4 as uuidv4} from 'uuid';
export default {
    name: "AddTodo",
    data() {
        return {
            title: '',
            status: '',
            quantity: '',
            vendor:''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                id: uuidv4(),
                title:this.title,
                quantity:this.quantity,
                vendor:this.vendor,
                status: 'New'
            }
            // Send to parent
            this.$emit('add-todo',newTodo);
            this.title = ''
            this.quantity = ''
            this.vendor = ''
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
    }

    input[type="text"]{
        flex: 10;
        padding: 5px;
    }

    input[type="submit"]{
        flex:2;
    }

</style>