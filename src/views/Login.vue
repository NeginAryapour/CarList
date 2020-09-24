<template>
  <div class="home">
    <div class="login-logo">
      <div class="carlist">CarList</div>
      <!-- <img src="../assets/taxi_blue.png" alt=""> -->
      <div class="adminpanel">admin panel</div>
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
          <br />
          <!-- <img src="../assets/eye_gray.png" alt=""> -->
          <div id="password_container">
            <input
              class="password_box"
              :type="passwordFieldType"
              name="password"
              v-model="input.password"
              placeholder="Password"
            />
            <button class="show_hide_btn" type="password" v-on:click="switchVisibility">show / hide</button>
          </div>

          <input class="forgot-password-btn" type="button" value="forgot password" />
        </div>
        <input class="login-btn" type="button" value="LOGIN" />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {

  el: "#password_container",
  name: "Login",
  components: {
    
  },
  
  data() {
    return {
      input: {
        username: "",
        password: "",
        // passwordFieldType: "password",
        passwordFieldType :"password"
      },
    };
  },

  methods: {
    login() {
      if (this.input.username != "" && this.input.password != "") {
        if (
          this.input.username == this.$parent.mockAccount.username &&
          this.input.password == this.$parent.mockAccount.password
        ) {
          this.$emit("authenticated", true);
          this.$router.replace({ name: "secure" });
        } else {
          console.log("The username and / or password is incorrect");
        }
      } else {
        console.log("A username and password must be present");
      }
    },
    switchVisibility() {
      this.passwordFieldType =
        this.passwordFieldType === "password" ? "text" : "password";
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

#password_container {
  background: none;
  
}

.show_hide_btn {
  width: 5%;
  display: inline-block;
  display: inline-block;
  *display: inline;
  zoom: 1;
  vertical-align: top;
  font-size: 12px;
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
  height: 2px;

  border: none;
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
  -webkit-box-shadow: 0 0 0 30px rgb(196, 196, 196) inset !important;
  -webkit-animation-fill-mode: both;

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
  color: #00acc2;
  outline: none;
}

.forgot-password-btn:active {
  /* border-color: white; */
}

.login-btn {
  width: 100px;
  height: 60px;
  margin: 0px 315px;
  border-radius: 35px;
  display: block;
  font-size: 16px;
  background-color: #00acc2;
  color: white;
  border: none;
  outline: none;
  box-shadow: 0px 0px 12px -2px rgba(0, 0, 0, 0.3);
  transition: background-color 0.4s ease;
  overflow: hidden;
}

.login-btn:hover {
  background: white;
  color: #00acc2;
  box-shadow: 0px 0px 12px -2px rgba(0, 0, 0, 0.3);
  border: none;
}

.login-btn:active {
  background: #00acc2;
  color: white;
}
</style>
