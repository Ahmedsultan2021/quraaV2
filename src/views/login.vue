<template>
  <navbar />

  <div class="container">
    <div class="row">
      <div class="col">
        <div class="login_logo">
          <img src="../../public/logo1.png" alt="" />
          <p class="login_p">جريدة قراء</p>
        </div>
        <div class="form">
          <form action="">
            <label for=""> الاسم </label>
            <input required type="text" name="name" id="input" v-model="name" />
            <label for=""> البريد الالكتروني</label>
            <input
              required
              type="email"
              name="email"
              id="input"
              v-model="email"
            />
            <div class="pass_div">
              <label for=""> كلمه المرور </label>
              <input
                required
                type="password"
                id="input_pass"
                v-model="password"
              />
              <img @click="toggele_show" :src="show_pass_img_url" alt="" />
            </div>
            <button @click="login_go">log in</button>
          </form>
        </div>
      </div>
    </div>
  </div>
  <foot />
</template>
<script>
import foot from "@/components/foot.vue";
import navbar from "@/components/navbar.vue";
export default {
  components: {
    navbar,
    foot,
  },
  data() {
    return {
      name: "",
      email: "",
      password: "",
      show_pass: false,
      show_pass_img_url: "view.png",
    };
  },
  methods: {
    login_go() {
      if (this.name && this.password && this.email) {
        this.$router.push({
          name: "text_editor",
        });
      } else {
        // alert("fill input")
        // document.getElementById('input').placeholder="Y should fill this input "
      }
    },
    toggele_show() {
      this.show_pass = !this.show_pass;
      if (this.show_pass) {
        document.getElementById("input_pass").type = "text";
        this.show_pass_img_url = "hide.png";
      } else if (!this.show_pass) {
        document.getElementById("input_pass").type = "password";
        this.show_pass_img_url = "view.png";
      }
    },
  },
};
</script>
<style scoped>
* {
  font-family: "Cairo", sans-serif;
}
.row {
  display: flex;
  justify-content: center;
  align-items: center;
}
h1 {
  text-align: center;
}
.col {
  text-align: center;
  /* height: 100vh; */
  border-radius: 20px;
  /* width: 200px; */
}
.login_logo {
  margin: 20px;
}
img {
  border-radius: 0px;
  height: 140px;
}
.login_p {
  color: var(--main-color);
  display: block;
  font-weight: 900;
  font-size: 40px;
}
.form {
  display: flex;
  justify-content: center;
}
form {
  width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: end;
  align-items: end;
  padding: 10px 10px;
}
.pass_div {
  width: 100%;
  text-align: end;
  position: relative;
}
.pass_div img {
  position: absolute;
  height: 30px;
  right: 0;
  top: 44%;
  margin: 0 5px;
}
input {
  width: 100%;
  margin: 10px 0;
  padding: 10px;
  background-color: rgb(246, 246, 246);
  border: none;
}
input:hover{
  border: var(--main-color) 2px solid;

}
label {
  color: black;
  font-weight: bold;
}
button {
  width: 70%;
  margin: 30px auto;
  text-align: center;
  border: none;
  background-color: var(--main-color);
  padding: 10px;
}
@media only screen and (max-width: 700px) {
  .container {
    position: relative;
    top: 50px;
    margin: 0px;
  }
  img {
    height: 100px;
  }
  form {
    width: 100%;
  }
}
</style>
