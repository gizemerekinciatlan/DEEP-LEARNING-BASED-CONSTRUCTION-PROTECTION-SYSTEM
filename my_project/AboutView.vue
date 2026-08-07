<template>
  <div>
    <header style="height: 100px; margin-bottom: -30px">
      <img class = "logo_img" src="../assets/logo.jpg" alt="">
      <nav style="margin-top: -30px; padding: 10px">
            <ul class="nav_links" >
                <li v-for="(items, index) in titles" :key="items" :class="{active: index === num}" @click="itemclick(index)"><a>{{items}}</a></li>
            </ul>
        </nav>
        <a href="" style="margin-top: -30px" class="cta"><button>Sign Out</button></a>
    </header>
    <div class="line"></div>
    <el-tabs tab-position="left" style="height: 600px; ">
        <el-tab-pane label="Machine 1" style="height: 600px">
          <div class="video">
            <video 
              class="video_show" 
              src="../assets/videos/1.mp4"
              autoplay
              ></video>
          </div>
        </el-tab-pane>
      </el-tabs>
  </div>
  
</template>
<script>
  export default {
    data() {
      return {
        titles: ['Machine Map', 'Videos', 'Message'],
        activeName: 'first',
        num: 0,
        longitude: '',
        latitude: '',
        addList: [],
      };
    },
    methods: {
      setadd (){
        this.addList.push({
          lon: this.longitude,
          lat: this.latitude
        })
      },
      handleClick(tab, event) {
        console.log(tab, event);
      },
      show_video(){
        this.$router.push('/about')
        console.log('1111')
      },
      remove(index) {
        this.addList.splice(index, 1)
      },
      itemclick(index){
        this.num = index
        console.log(this.num)
      },
    }
  };
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap');


*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    background-color: #e9eef1;
}


li,a,button{
    font-family: "Montserrat",sans-serif;
    font-weight: 500;
    font-size: 16px;
    color: white;
    text-decoration: none;
}
header{
    display: flex;
    justify-content: space-between;
    align-items:center;
    padding: 10px 10%;
}
.blue {
  color: #4b70e2;
}
.line {
  width: 100%;
  height: 1px;
  border-top: solid rgba(0, 0, 0, .16) 1px;
  margin-bottom: 15px;
}
.input {
  display: flex;
  height: 40px;
  width: 50%;
  margin-bottom: 15px;
}
.map_body{
  margin-left: 5%;
  width: 90%;
}
.map {
  width: 100%;
  height: 50px;
}
.active {
  color: #4b70e2;
}

.active a {
  padding: 3px;
  border-bottom: 2px solid black;
}
.logo_img {
  margin-top: -30px;
  width: 75px;
  height: 70px;
}
.video {
  height: 600px;
}
.video_show {
  margin-top: -50px;
  width: 70%;
  height: 600px;
}
.logo{
    cursor: pointer;
    order: 3;
    margin-left: auto;
}

.nav_links{
    list-style: none;
}

.nav_links li{
    display: inline-block;
    padding: 0px 20px;
}



.nav_links li a{
    transition: all 0.3s ease 0s;
}
.nav_links li a:after{
    color: #4b70e2;
}
/* 
.nav_links li a:hover{
    color: #4b70e2;
} */

.nav_links li a:active{
    color: #4b70e2;
}
 button{
    padding: 9px 25px;
    background-color: #4b70e2;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    transition: all 0.3s ease 0s;
 }

 button:hover{
    background-color: #4b70e2;
 }
.map {
  width: 100%;
  height: 600px;
}
</style>