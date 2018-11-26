<template>
<div>
  <nav class="navbar navbar-light bg-light sticky-top">
        <a class="navbar-brand">
            <img src="../assets/logo2.jpg" width="50" height="50" alt="">
            The BookShop
        </a>  
     <div>
          <input class="form-control mr-sm-2" type="text" placeholder="Search Books" aria-label="Search">
    </div>     
   
    </nav>
</div>

</template>
<script>
export default {
    
    name: "BookShopNavbar"
}
</script>
<style scoped>
.navbar {
  position: sticky;
  display: flex;
  height: 65px;
  background-color: #e9e9e9;

}
.navbar-logo{
  float: left;
    display: block;
    color: black;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
    font-size: 17px;
}
.navbar-logo  a:hover {
 background-color: #ddd;
    color: black;
}
.navbar.log  a.active {
 background-color: #2196F3;
    color: white;
}
.navbar-search {
     float: right;
    padding: 6px;
    border: none;
    margin-top: 8px;
    margin-right: 16px;
    font-size: 17px;
}
</style>

