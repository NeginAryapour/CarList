<template>
  <div>
    <!-- <h1>Vertical Menu</h1> -->

    <div class="vertical-menu">
      <div>hi</div> 
      <a href="#dashboard" >Dashboard</a>
      <a href="#drivers" class="active">Drivers</a>
      <a href="#cars">Cars</a>
      <a href="#setting">setting </a>
      <a href="#logout">Log out</a>
    </div>

    
  </div>
</template>

<script>
export default {};
</script>

<style>
.vertical-menu {
  height: 100%; /* Full-height: remove this if you want "auto" height */
  width: 250px; /* Set the width of the sidebar */
  position: fixed; /* Fixed Sidebar (stay in place on scroll) */
  z-index: 1; /* Stay on top */
  top: 0; /* Stay at the top */
  left: 0;
  background-color: white; /* Black */
  overflow-x: hidden; /* Disable horizontal scroll */
  padding-top: 20px;
}

.vertical-menu a {
  background-color:white;
  color: #d3d3d4;
  display: block;
  padding: 20px;
  /* margin-top: 0px; */
  padding-left: 70px;
  text-decoration: none;
  display: block;
  /* margin: inherit; */

}

/* @media screen and (max-height: 450px) {
  .sidenav {padding-top: 15px;}
  .sidenav a {font-size: 18px;}
} */

.vertical-menu a:hover {
  /* background-color: ; */
  color: #00acc2;

  /* border-color: #00acc2; */
  /* border-block-color: #00acc2; */
}

.vertical-menu a.active {
  background-color: #00acc2;
  color: white;
  border-radius: 30px;
}
</style>