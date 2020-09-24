<template>
  <div class="home">
    <div id="carlist">CarList</div>
    <div class="container">
      <div class="white-box">
        <div class="login-txt">Login</div>
        <hr />
        <div id="login">
          <input type="text" name="username" v-model="input.username" placeholder="Username" />
          <br/>
          <input type="text" name="password" v-model="input.password" placeholder="Password" />
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Login",
  components: {},
  data() {
    return {
      input: {
        username: "",
        password: "",
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
  /* -webkit-box-shadow: 0 1px 20px rgba(0, 0, 0, 0.13); */
  /* -moz-box-shadow: 0 1px 20px rgba(0, 0, 0, 0.13); */
  box-shadow: 12px 12px 2px rgba(0, 0, 0, 0.02);
  /* 
  -webkit-border-radius: 5px;
  -moz-border-radius: 25px;
  -ms-border-radius: 25px;
  -o-border-radius: 25px; */
  border-radius: 15px;
}

#carlist {
  font-size: 49px;
  font-weight: normal;
  color: rgba(19, 3, 3, 0.5);
  padding: 20px;
}
.login-txt {
  background-color: white;
  color: #00acc2;
  font-size: 30px;
  font-weight: bold;
  padding: 10px;
  /* margin-top: ; */
}

hr {
  height: 2px;
  /* color: yellow; */
  border: none;
}

#login {
  /* width: 500px; */
  /* border: 1px solid red; */
  background-color:gray;
  margin: auto;
  margin-top: 20px;
  padding: 20px;
}


br {
  /* height: 80px;
  padding: 20px;
  border: none; */
}
/* .container {
  position: absolute;
  margin: 0;
  width: 100%;
  background: #f4f5f4;
  min-height: 600px;
} */
</style>
