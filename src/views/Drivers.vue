<template>
  <div>
    <!-- <h1>Vertical Menu</h1> -->

    <!-- <div class="vertical-menu">
      <div>hi</div> 
      <a href="#dashboard" >Dashboard</a>
      <a href="#drivers" class="active">Drivers</a>
      <a href="#cars">Cars</a>
      <a href="#setting">setting </a>
      <a href="#logout">Log out</a>
    </div> -->
  <div  class="card">
    <table>
      <tr class="table_heading">
        <th><input type="checkbox" name="name1" />&nbsp;</th>
        <th>id</th>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Car Name</th>
        <th>Email</th>
      </tr>
      <tr class="table_data">
        <td><input type="checkbox" name="name2" />&nbsp;</td>
        <td  >1</td>
        <td>negin</td>
        <td>ar</td>
        <td>sf5</td>
        <td>negin@gmail.com</td>
      </tr>
    </table>
    </div>

    
  </div>
</template>

<script>
export default {};
</script>

<style>

input[type="checkbox"] {
  /* box-shadow: 0 0 0 3px orange; */
  margin-left: 50px;
}


th{
  /* background-color: olivedrab; */
  background-color: rgba(211, 211, 212, 1);
  height: 50px;
}

td{
  background:white;
  height: 67px;
  width: 156px;
}

.card{
  width: 80%;
  /* display: center; */
}
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