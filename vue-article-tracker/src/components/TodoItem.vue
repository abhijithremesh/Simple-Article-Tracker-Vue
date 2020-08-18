<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        
        <b-card>
            <b-card-text>
               <br>
               Article: {{todo.title}}
               <br>
               Quantity: {{todo.quantity}}
               <br>
               Vendor: {{todo.vendor}}
               <br>
               Status: {{todo.status}}
               <br>
               <br>
            </b-card-text>

            <b-button variant="primary" v-on:click="picked" >PICK</b-button>
            &nbsp; 
            
            <b-button variant="primary" v-on:click="dispatched">DISPATCH</b-button>
            &nbsp;

            <b-button variant="primary" v-on:click="issued" >GOODS ISSUE</b-button>
            &nbsp;

            <b-button variant="primary" v-on:click="received">GOODS RECEIPT</b-button>
            &nbsp;

            <button  @click="$emit('del-todo', todo.id)" class="del"> DELETE</button>

        </b-card>
    </div>

   
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods:{
        picked(){
           this.todo.status = "picked";
        },
        dispatched(){
           this.todo.status = "dispatched";
        },
        issued(){
           this.todo.status = "issued";
        },
        received(){
           this.todo.status = "received";
        }
    }
}
</script>

<style scope>
    .todo-item{
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .del {
        background: #a51313;
        color: #fff;
        border: black;
        padding: 5px 9px;
        /* border-radius: 50%; */
        cursor: pointer;
        float: right;
    }

    .hehe {
        padding-left:5em;
    }
</style>