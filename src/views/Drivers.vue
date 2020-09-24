<template>
  <div>
    <!-- <h1>Vertical Menu</h1> -->

    <div class="vertical-menu">
      <a href="#" >Dashboard</a>
      <a href="#" class="active">Drivers</a>
      <a href="#">Cars</a>
      <a href="#">setting </a>
      <a href="#">Log out</a>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.vertical-menu {
  width: 250px;
  /* height: 1000px; */
}

.vertical-menu a {
  background-color:white;
  color: #d3d3d4;
  display: block;
  padding: 20px;
  padding-left: 70px;
  text-decoration: none;
  /* margin: inherit; */

}

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