<template>
    <div>
  <h1>{{title}}</h1>
    <ul>
        <li v-for="(item,index) in lists">{{item.id}}|{{item.title}}|{{item.time}} <button v-on:click="del(index)"  >delete</button> </li>
    </ul>
        <input placeholder="id" v-model="id"/>
        <input placeholder="title" v-model="tit"/>
        <input placeholder="time" v-model="time"/>
        <input type="button" v-on:click="add" value="add"/>
    </div>
</template>

<script>
    export default {
        name: "simple-list",
        mounted:function(){
            console.log("###");
        },
        data:function(){
          return {
              lists:[
                  {id:1,title:'xxx1',time:'2019-12-12'},
                  {id:2,title:'xxx2',time:'2019-12-13'},
                  {id:3,title:'xxx3',time:'2019-12-14'},
              ],
              title:"title",
              id:'',
              tit:'',
              time:''
          }
        },
        methods:{
            add:function(){
               var newItem={
                   id:this.id,
                   title:this.tit,
                   time:this.time,
               };
               this.lists.push(newItem);
            },
            del:function(id){
                this.lists.splice(id,1);
            },
        }
    }
</script>

<style scoped>

</style>