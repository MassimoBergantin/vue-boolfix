
<template>
<div class="container-fluid">
    <div class="header-container row">
        <div class="logo-container col-6">
            <div class="logo-content">
                <a href="main.vue"><img src="../assets/logo.png" alt="logo-Netflix"> </a>  
            </div>
              <div class="nav col-12">
                    <ul>
                        <li>Home</li>
                        <li>Serie Tv</li>
                        <li>Film</li>
                        <li>Originali</li>
                        <li>Aggiunti di recente</li>
                        <li>La mia lista</li>
                    </ul>
                </div>
        </div>

       <div class="icon-container col ">
            <div class="icon-content">
                <ul>
                    <li>BAMBINI</li>
                    <li><i class="fas fa-bell"></i></li>
                </ul>
            </div>
       </div> 
    </div>   
</div>                
</template>


<script>
export default {
    name: 'Header',
    data() {
        return{
            searchString: "",
        }
    },
}
</script>


<style lang="scss" scoped>
    .header-container {
        color:white;
        background-color: rgb(37, 37, 37);
        height: 80px;
        li{
            list-style:none;
            display: inline-block;
            margin-left:10px;
            color:white;
        }
    
        .logo-container{
            display: flex;
            align-items: center;
        }
        .logo-content{
            img{
                width: 150px;
            }
        }
        
        .icon-container{
            display: flex;
            align-items: center;
            justify-content: flex-end;
        }
     
    }
</style>