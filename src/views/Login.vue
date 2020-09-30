<template>
  <div class="home">
    <div class="login-logo">
      <div class="carlist">CarList</div>

      <!-- <img src="../assets/taxi_blue.png" alt=""> -->
      <div class="adminpanel">admin panel</div>
      <img class="car_logo" src="../assets/taxi_blue.png" alt />
    </div>
    <div class="container">
      <div class="white-box">
        <div class="login-txt">Login</div>
        <hr />
        <div id="login">
          <input
            class="username_box"
            type="text"
            name="username"
            v-model="input.username"
            placeholder="Username"
            autocomplete="off"
          />
          <br  />
          <!-- <img src="../assets/eye_gray.png" alt=""> -->
          <div id="password_container">
            <input
              class="password_box"
              :type="passwordFieldType"
              name="password"
              v-model="input.password"
              placeholder="Password"
            />
            <button class="show_hide_btn" type="password" v-on:click="switchVisibility">
              <img class="icon" src="../assets/eye_gray.png" />
            </button>
          </div>

          <input class="forgot-password-btn" type="button" value="forgot password" />
        </div>
        <input class="login-btn" type="button" value="LOGIN" v-on:click="login()" />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
const axios = require('axios');

export default {
  el: "#password_container",
  name: "Login",
  components: {},

  data() {
    return {
      input: {
        username: "",
        password: "",
        // passwordFieldType: "password",
      },
      passwordFieldType: "password",
      eye_url: "../assets/eye_gray.png",
    };
  },

  methods: {
    async login() {
      const username = this.input.username;
      const password = this.input.password;
      console.log(username, password);
      const response = await axios.post('http://localhost:1337/auth/local', {identifier: username, password});
      if (response.status !== 200) {
        // Error
        console.error('error')
      } else {
        const {first_name, last_name, token} = response.data;
        window.localStorage.setItem('token', token);
        window.localStorage.setItem('name', first_name + " " + last_name);
        this.$router.push('drivers');
      }
    },
    switchVisibility() {
      this.passwordFieldType =
        this.passwordFieldType === "password" ? "text" : "password";
      this.eye_url =
        this.passwordFieldType === "password"
          ? "../assets/eye_gray.png"
          : "../assets/invible.png";
    },
  },
};
</script>

<style>
* {
  background-color: #ececed;
}
.white-box {
  width: 500px;
  height: 400px;
  margin-top: 60px;
  margin-left: auto;
  margin-right: auto;

  background: rgba(255, 255, 255);
  padding: 30px;

  box-shadow: 12px 12px 2px rgba(0, 0, 0, 0.02);

  border-radius: 15px;
}
.car_logo {
  margin-left: 150px;
  margin-top: -150px;
  width: 32px;
  height: 32px;
}

.icon {
  background: none;
}

#password_container {
  background: none;
  display: flex;
}
#password_container button {
  margin-left: -3rem;
  margin-top: 1rem;
}

#password_container button:focus {
  outline: 0;
}

.show_hide_btn {
  width: 5%;
  display: inline-block;
  display: inline-block;
  *display: inline;
  zoom: 1;
  vertical-align: top;
  font-size: 12px;
  background: none;
  outline: none;
  border: none;
}

.show_hide_btn :active {
  outline: none;
}

.carlist {
  font-size: 30px;
  font-weight: normal;
  color: rgba(19, 3, 3, 0.5);
  padding: 30px;
  padding-bottom: 0;
}
.adminpanel {
  font-size: px;
  font-weight: normal;
  color: rgba(19, 3, 3, 0.36);
  padding: 30px;
  padding-top: 0;
}

.login-txt {
  background-color: white;
  color: #00acc2;
  font-size: 30px;
  font-weight: bold;
  padding: 10px;
}

hr {
  height: 2.5px !important;
  background-color: rgb(196, 196, 196, 0.1) !important;
  border: 0 none !important;
}

#login {
  background-color: white;
  margin: auto;
  margin-top: 20px;
  padding: 10px;
  border-radius: 15px;
  outline: none;
}

.username_box {
  padding: 20px;
  margin-top: 0px;
  background-color: rgb(196, 196, 196, 0.1);
  width: 400px;
  height: 55px;
  outline-color: #00acc2;
  border: none;
  /* border-radius : 35px; */
}

.password_box {
  padding: 20px;
  margin-top: 20px;
  background-color: rgb(196, 196, 196, 0.1);
  width: 95%;
  height: 55px;
  outline-color: #00acc2;
  border: none;
  display: inline-block;
  display: inline-block;
  *display: inline;
  zoom: 1;
  vertical-align: top;
  font-size: 12px;
}

input[type="text"]::content {
  border: 1px solid #d3d3d4;
  background-color: #00acc2;
}

input[type="text"]:hover {
  border: 2px solid white;
  /* background-color: #00acc2; */
}

input[type="password"]:hover {
  border: 2px solid white;
  /* background-color: #00acc2; */
}

input:-webkit-autofill,
input:-webkit-autofill:hover,
input:-webkit-autofill:focus,
input:-webkit-autofill:active {
  -webkit-box-shadow: 0 0 0 30px rgb(196, 196, 196, 0.5) inset !important;
  -webkit-animation-fill-mode: both;
  /* -webkit-border-image: none; */

  outline: none;
}

::placeholder {
  color: #d3d3d4;
  font-size: 20px;
}

.forgot-password-btn {
  border: none;
  background: none;
  margin-top: 5px;
  color: #00acc2 !important;
  outline: none;
}

.forgot-password-btn:active {
  /* border-color: white; */
  color: #d3d3d4 !important;
}

.login-btn {
  width: 100px;
  height: 60px;
  margin: 0px 315px;
  border-radius: 35px;
  display: block;
  font-size: 16px;
  background-color: #00acc2;
  color: white !important;
  border: none;
  outline: none;
  box-shadow: 0px 0px 12px -2px rgba(0, 0, 0, 0.3);
  transition: background-color 0.4s ease;
  overflow: hidden;
}

.login-btn:hover {
  background: white;
  color: #00acc2 !important;
  font-weight: bolder;
  box-shadow: 0px 0px 12px -2px rgba(0, 0, 0, 0.3);
  /* border-color: #00acc2; */
  /* border-width: medium; */
}

.login-btn:active {
  background: #00acc2;
  color: white !important;
  font-weight: bolder;
}
</style>
