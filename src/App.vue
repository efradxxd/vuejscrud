<template>
  <div id="app">
   <h1>{{lists}}</h1>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
    
  },
  created: function(){
      //this.deleteUser();
      this.getUsers();
      //this.postUsers();
      this.putUsers();
  },
  data() {
    return {
      lists:[]
    }
  },
  methods:{
    getUsers:function(){
      this.$http.get('https://o2dstvq9sb.execute-api.us-west-2.amazonaws.com/dev/articles').then(function(response){
        this.lists=response;
        console.log(this.lists);
      }).catch(e=>{
          console.log(e);
      });
      
    },
    postUsers: function(){
      this.$http.post('https://o2dstvq9sb.execute-api.us-west-2.amazonaws.com/dev/articles',{
        ID : "",
        ARTICLE : {
            Author : "UNDERTAKER",
            Content : "Q",
            DT : "Q",
            Location : "Q",
            PublishStatus : "Q",
            Section : "Q",
            Tags : "Q",
            Title : "Q"
        },
        IMG : {
            Author : "Q",
            DT : "Q",
            Location : "Q",
            S3DIR : "Q"
        }
      }).then(function(response){
          console.log(response);
      }).catch(e=>{
          console.log(e);
      });
    },
    deleteUser: function(){
        this.$http.delete('https://o2dstvq9sb.execute-api.us-west-2.amazonaws.com/dev/articles/1548135295738JB5').then(function(response){
            console.log(response);
        }).catch(e=>{
            console.log(e);
        });
    },
    putUsers:function(){
        var identificador='1548135278430DD6';
        this.$http.put('https://o2dstvq9sb.execute-api.us-west-2.amazonaws.com/dev/articles/'+identificador,{
        ID : identificador,
        ARTICLE : {
            Author : "UNDERTAKERSSSSSSS",
            Content : "Q",
            DT : "Q",
            Location : "Q",
            PublishStatus : "Q",
            Section : "Q",
            Tags : "Q",
            Title : "Q"
        },
        IMG : {
            Author : "Q",
            DT : "Q",
            Location : "Q",
            S3DIR : "Q"
        }
      }).then(function(response){
          console.log(response);
      }).catch(e=>{
          console.log(e);
      });
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
