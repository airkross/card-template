<template>
  <nav class="nav">
    <div class="container">
      <div class="nav-block">
        <div class="burger-block">
          <button class="burger" @click="showMenu()"></button>
        </div>

        <div class="nav-menu" ref="menu">
          <ul>
            <li class="nav-menu-item active">
              <a href="#" class="nav-menu-link">Home</a>
            </li>
            <li class="nav-menu-item">
              <a href="#" class="nav-menu-link">Marketplace</a>
            </li>
            <li class="nav-menu-item">
              <a href="#" class="nav-menu-link">Booster Packs</a>
            </li>
          </ul>
          <div class="play-btn-block">
            <button class="play-btn">Play</button>
          </div>
        </div>
        <div class="menu-user">
          <div class="record-block">
            <img src="@/assets/img/1.png" alt="record" />
            <img src="@/assets/img/f_circle.png" class="alert-circle" alt="circle" />
          </div>
          <div class="alert-block">
            <img src="@/assets/img/1.png" alt="alert" />
            <img src="@/assets/img/g_circle.png" class="alert-circle" alt="circle" />
          </div>
          <div class="money-block">
            <!-- <div><img src="../assets/img/gem.png" alt="gem"></div> -->
            <div class="gem"></div>
            <div>{{money}}</div>
          </div>
          <div class="user-block">
            <div class="border-icon"></div>
            <img src="../assets/img/u_elipse.png" class="u_circle" alt="u_cirlce" />
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      money: 142
    };
  },
  methods: {
    showMenu() {
      if (this.$refs.menu.style.display === "block") {
        this.$refs.menu.style.display = "none";
      } else {
        this.$refs.menu.style.display = "block";
      }
    }
  }
};
</script>

<style scoped>
.nav {
  background: #242334;
  height: 72px;
  width: 100%;
  position: fixed;
  z-index: 999;
}

.nav-block {
  display: flex;
}
.nav-menu {
  display: flex;
  margin-left: auto;
}
.menu-user {
  margin-left: auto;
}
ul {
  display: flex;
  list-style-type: none;
}
.nav-menu-link {
  text-decoration: none;
  text-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 14px;
  font-weight: 400;
  letter-spacing: 1.13px;
  padding: 26px 34px;
  display: flex;
  align-items: center;
}
.play-btn-block {
  display: flex;
  align-items: center;
}
.play-btn {
  margin-left: 10px;
  background: none;
  border: none;
  outline: none;
  cursor: pointer;
  /* background: url("../assets/img/play.png") no-repeat; */
  /* background-size: cover; */
  width: 106px;
  height: 42px;
  box-shadow: 0 15px 11px rgba(9, 10, 15, 0.15);
  border-radius: 21px;
  border: 2px solid #9d9acc;
  background-color: #6f6d99;
  background-image: linear-gradient(to right, #242333 0%, #3c3b53 100%);
  text-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 14px;
  font-weight: 400;
  letter-spacing: 1.13px;
}
.record-block {
  position: relative;
  padding-top: 8px;
  cursor: pointer;
}
.alert-block {
  position: relative;
  padding-top: 8px;
  margin-left: 35px;
  margin-right: 30px;
  cursor: pointer;
}
.menu-user {
  display: flex;
  align-items: center;
}
.alert-circle {
  position: absolute;
  top: 2px;
  right: -4px;
}
.gem {
  background: url("../assets/img/gem.png") no-repeat;
  background-size: cover;
  background-position: center;
  width: 18px;
  margin-bottom: -6px;
  margin-top: 6px;
  margin-left: 10px;
  margin-right: 8px;
}
.money-block {
  background: url("../assets/img/gem-play.png") no-repeat;
  background-size: cover;
  width: 85px;
  height: 38px;
  box-shadow: 0 15px 11px rgba(9, 10, 15, 0.15);
  border-radius: 21px;
  border: 2px solid #a3429c;
  background-color: #6f6d99;
  background-image: linear-gradient(to right, #242333 0%, #3c3b53 100%);
  text-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  color: #cecbff;
  font-family: "Geomanist-Book";
  font-size: 14px;
  font-weight: 400;
  color: #ffffff;
  letter-spacing: 1.13px;
  display: flex;
  line-height: 38px;
  margin-right: 30px;
}
.user-block {
  position: relative;
  cursor: pointer;
}
.border-icon {
  border-radius: 50%;
  border: 2px solid #9c99cb;
  height: 50px;
  width: 50px;
}
.u_circle {
  position: absolute;
  top: 38px;
  right: -4px;
}
.active {
  background: url("../assets/img/active.png") no-repeat;
  background-size: cover;
  border-bottom: 2px solid #df5ab5;
}
.burger-block{
  display: none;
}
@media screen and (min-width: 992px){
  .nav-menu{
    display: flex;
  }
}
@media screen and (max-width: 991px) {
  .burger-block {
    display: block;
    display: flex;
    align-items: center;
  }
  .burger {
    background: none;
    border: none;
    cursor: pointer;
    background: url("../assets/img/burger.png") no-repeat;
    background-size: cover;
    height: 30px;
    width: 30px;
  }
  .nav-menu {
    display: none;
    flex-direction: column;
    margin-left: 0;
    align-items: flex-start;
    position: absolute;
    top: 80px;
    background: rgba(36, 35, 52, 0.9);
    width: 90%;
    /* padding: 15px; */
    padding-left: 30px;
    padding-top: 15px;
    border-radius: 15px;
    padding-bottom: 15px;
    max-width: 830px;
  }
  .nav-block {
    position: relative;
  }
  .play-btn {
    margin-left: 0;
  }
  .nav-menu ul {
    /* display: none; */
    flex-direction: column;
    align-items: flex-start;
  }
  .menu-user {
    height: 72px;
  }
  .nav-menu-link {
    padding: 0;
    display: block;
    width: 130px;
    height: 55px;
    line-height: 55px;
    text-align: left;
  }
}
@media screen and (max-width: 575px){
  .alert-block{
    margin-left: 5px;
    margin-right: 5px;
  }
  .money-block{
    margin-right: 5px;
  }
}
</style>