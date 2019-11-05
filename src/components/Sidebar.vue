<template>
  <div>
    <aside class="sidebar">
      <div class="sidebar-title">
        <div class="title-block">
          <h2>Related News</h2>
        </div>
      </div>
      <div v-for="index in 3" :key="index" class="sidebar-cards">
        <div class="sidebar-card">
          <div class="card-footer">
            <h5>Welcome to Nethernite</h5>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt</p>
          </div>
        </div>
      </div>
    </aside>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.title-block h2 {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 18px;
  font-weight: 400;
  letter-spacing: 0.72px;
}
.title-block {
  padding-top: 33px;
  padding-bottom: 33px;
}
.sidebar-card {
  background: url("../assets/img/s-pers.png") no-repeat;
  background-size: cover;
  max-width: 442px;
  width: 100%;
  height: 262px;
  position: relative;
  margin-bottom: 42px;
}
.card-footer {
  border-radius: 0 0 10px 10px;
  background-color: rgb(36, 35, 51, 0.9);
  position: absolute;
  bottom: 0;
  padding: 24px 26px;
}
.card-footer h5 {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 18px;
  font-weight: 400;
  letter-spacing: 0.72px;
  margin-bottom: 10px;
}
.card-footer p {
  color: #9d9acc;
  font-family: "Geomanist-Book";
  font-size: 14px;
  font-weight: 400;
  letter-spacing: 0.56px;
}
@media screen and (max-width: 991px) {
}
</style>