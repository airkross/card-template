<template>
  <div>
    <div class="top"></div>
    <main class="main">
      <div class="container">
        <div class="content">
          <div class="main-content">
            <div class="back-block">
              <a href="#" class="back-link">
                <div class="back-block-img">
                  <img src="../assets/img/lar.png" alt="back" />
                </div>
                <span>Back</span>
              </a>
            </div>
            <div class="wrapper-nav">
              <div class="content-nav">
                <div class="content-back">
                  <a href="#" class="nav-link">
                    <div class="nav-back-block">
                      <img src="../assets/img/b.png" alt="back" />
                    </div>
                    <span>See Previous</span>
                  </a>
                </div>
                <div class="content-next">
                  <a href="#" class="nav-link">
                    <span>See Next</span>
                    <div class="nav-next-block">
                      <img src="../assets/img/n.png" alt="next" />
                    </div>
                  </a>
                </div>
              </div>
            </div>
            <article class="record">
              <div class="record-body">
                <div class="record-img">
                  <img src="../assets/img/pers.png" alt="preview" />
                </div>
                <h3>The International 2018 Collector’</h3>
                <span class="date">July 24, 2018</span>
                <p class="record-text">
                  Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                  Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
                  when an unknown printer took a galley of type and scrambled it to make a type
                  specimen book. It has survived not only five centuries, but also the leap into
                  electronic typesetting, remaining essentially unchanged. It was popularised in
                  the 1960s with the release of Letraset sheets containing Lorem Ipsum passages
                </p>
                <p class="record-text">
                  Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                  Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.
                </p>
              </div>
              <div class="record-footer">
                <div class="footer-comment">
                  <div class="block-like" @click="likes===345?likes++:likes=345">
                    <img src="../assets/img/like.png" alt="like" />
                  </div>
                  <div class="likes">{{likes}}</div>
                  <div class="rating">7.649</div>
                </div>
                <div class="footer-social">
                  <div class="social-block ">
                    <a href="#" class="social-link">
                      <img src="../assets/img/a.png" alt="recomend" />
                    </a>
                  </div>
                  <div class="social-block mx">
                    <a href="#" class="social-link">
                      <img src="../assets/img/fb.png" alt="facebook" />
                    </a>
                  </div>
                  <div class="social-block">
                    <a href="#" class="social-link">
                      <img src="../assets/img/tw.png" alt="twitter" />
                    </a>
                  </div>
                </div>
              </div>
            </article>
            <div class="comments">
              <div class="comments-header">
                <div class="comments-header-left">
                  <div class="comment-img">
                    <img src="../assets/img/comm.png" alt="comments" />
                  </div>
                  <span class="comments-count">Comments:</span>
                  <span class="com-amount">{{comments.length}}</span>
                </div>
                <div class="comments-header-right">
                  <button class="com-btn active">Popular</button>
                  <button class="com-btn">Recent</button>
                </div>
              </div>
              <div class="comments-body">
                <div class="comment-input-block">
                  <input
                    type="text"
                    class="comment-input"
                    v-model="comment"
                    @keyup.enter="addComment()"
                    placeholder="Type comment here.."
                  />
                  <button class="comment-arrow" @click="addComment()"></button>
                </div>
                <div class="comment-view" v-for="(comment, index) in getComments" :key="index">
                  <div class="comment-user-icon">
                    <img src="../assets/img/user.png" alt="user" />
                  </div>
                  <div class="comment-info">
                    <div class="u-name">
                      <span class="name">Svetlakov</span>
                      <span class="com-date">{{comment.date}}</span>
                    </div>
                    <p class="u-comment">{{comment.comment}}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="sidebar-content">
            <app-sidebar></app-sidebar>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import Sidebar from "@/components/Sidebar.vue";
export default {
  name: "Home",
  data() {
    return {
      likes: 345,
      commentsAmount: 48,
      comments: [
        {
          date: "4 November",
          comment: "Тестовый комментарий... Введите свой коммент ;)"
        }
      ],
      comment: ""
    };
  },
  methods: {
    addComment() {
      if (this.comment === "") {
        return;
      }
      const monthNames = [
        "January",
        "February",
        "March",
        "April",
        "May",
        "June",
        "July",
        "August",
        "September",
        "October",
        "November",
        "December"
      ];

      let date = new Date();
      date = date.getDate() + " " + monthNames[date.getMonth()];
      this.comments.push({
        date: date,
        comment: this.comment
      });
      this.comment = "";
    }
  },
  computed: {
    getComments() {
      return this.comments;
    }
  },
  components: {
    appSidebar: Sidebar
  }
};
</script>

<style scoped>
.top {
  height: 72px;
  width: 100%;
}
.comment-user-icon {
  margin-right: 17px;
}
.comment-view {
  display: flex;
  border-bottom: 2px solid rgba(157, 154, 204, 0.1);
  padding-bottom: 24px;
  margin-top: 34px;
}
.u-name {
  margin-bottom: 17px;
}
.u-comment {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 14px;
  font-weight: 400;
  line-height: 24px;
  letter-spacing: 0.56px;
}
.u-name .name {
  color: #9d9acc;
  font-family: "Geomanist-Book";
  font-size: 18px;
  font-weight: 400;
  letter-spacing: 0.72px;
}
.com-date {
  opacity: 0.5;
  color: #9d9acc;
  font-family: "Geomanist-Book";
  font-size: 16px;
  font-weight: 400;
  letter-spacing: 0.64px;
  margin-left: 13px;
}
.comment-input-block {
  max-width: 780px;
  width: 100%;
  height: 62px;
  font-family: "Geomanist-Book";
  font-size: 16px;
  font-weight: 400;
  letter-spacing: 0.64px;

  border-radius: 5px;
  background-color: rgba(157, 154, 204, 0.1);
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.comment-arrow {
  background: none;
  border: none;
  outline: none;
  background: url("../assets/img/arrow.png") no-repeat;
  width: 14px;
  height: 10px;
  cursor: pointer;
  margin-right: 27px;
  background-position: right;
}
.comment-input {
  background: none;
  outline: none;
  border: none;
  color: white;
  height: 100%;
  padding-left: 27px;
  padding-right: 27px;
  width: 100%;
  font-family: "Geomanist-Book";
  font-size: 16px;
  font-weight: 400;
  letter-spacing: 0.64px;
}
.com-btn {
  /* Style for "Popular" */
  padding-left: 9px;
  padding-right: 9px;
  color: #9d9acc;
  font-family: "Myriad Pro";
  font-size: 16px;
  font-weight: 400;
  /* Text style for "Popular" */
  color: #ffffff;
  letter-spacing: 0.64px;
  background: none;
  border: none;
  cursor: pointer;
  padding-bottom: 30px;
  margin-left: 30px;
  outline: none;
}
.active {
  border-bottom: 2px solid #df5ab5;
}
.comments {
  box-shadow: 0 22px 40px rgba(36, 35, 51, 0.45);
  border-radius: 15px;
  background-color: #242333;
  margin-top: 20px;
}
.comments-header-left {
  display: flex;
}
.comments-header {
  padding: 30px;
  padding-bottom: 0;
  display: flex;
  justify-content: space-between;
  border-bottom: 2px solid rgba(157, 154, 204, 0.1);
}
.comments-body {
  padding: 30px;
}
.comment-img {
  margin-right: 20px;
}
.comments-count {
  margin-right: 6px;
  color: #9d9acc;
  font-family: "Myriad Pro";
  font-size: 18px;
  font-weight: 400;
  font-family: "Myriad Pro";
  font-weight: 400;
  letter-spacing: 0.72px;
}
.com-amount {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-weight: 300;
  letter-spacing: 0.72px;
}
.content {
  display: flex;
}
.record {
  box-shadow: 0 22px 40px rgba(36, 35, 51, 0.45);
  border-radius: 15px;
  background-color: #242333;
  margin-top: 20px;
}
.record-body {
  padding: 25px 23px;
  border-bottom: 2px solid rgba(157, 154, 204, 0.1);
}
.record-footer {
  padding: 25px 23px;
  display: flex;
  justify-content: space-between;
}
.block-like img {
  cursor: pointer;
}
.likes {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 16px;
  font-weight: 400;
  line-height: 25px;
  letter-spacing: 0.64px;
  margin-left: 13px;
  margin-right: 90px;
}
.rating {
  color: #9d9acc;
  font-family: "Geomanist-Book";
  font-size: 16px;
  font-weight: 400;
  line-height: 25px;
  letter-spacing: 0.64px;
}
.footer-comment {
  display: flex;
}
.footer-social {
  display: flex;
}
.social-block {
}
.record h3 {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 22px;
  font-weight: 500;
  letter-spacing: 0.88px;
  margin-top: 27px;
  margin-bottom: 20px;
}
.record-img img {
  width: 100%;
}
.record-text {
  color: #9d9acc;
  font-family: "Geomanist-Book";
  font-size: 16px;
  font-weight: 400;
  line-height: 25px;
  letter-spacing: 0.64px;
  margin-top: 31px;
}
.date {
  opacity: 0.5;
  color: #9d9acc;
  font-family: "Geomanist-Book";
  font-size: 16px;
  font-weight: 400;
  letter-spacing: 0.64px;
}
.main-content {
  max-width: 830px;
  width: 100%;
  margin-right: 33px;
}
.sidebar-content {
  max-width: 442px;
  width: 100%;
  /* height: 200px; */
}
.main {
  background: #2f2e41 url("../assets/img/bg.png") no-repeat;
  background-size: cover;
  background-position: center;
  padding-bottom: 30px;
  z-index: 99;
}
.top-block {
  padding-top: 38px;
  padding-bottom: 35px;
  display: flex;
}
.back-block {
  max-width: 830px;
  width: 100%;
  margin-right: 17px;
  margin-top: 33px;
  margin-bottom: 33px;
}
.back-link {
  display: flex;
  text-decoration: none;
  align-items: center;
  max-width: 90px;
}
.back-link span {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 18px;
  font-weight: 400;
  letter-spacing: 0.72px;
  margin-left: 21px;
}
.title-block h2 {
  color: #ffffff;
  font-family: "Geomanist-Book";
  font-size: 18px;
  font-weight: 400;
  letter-spacing: 0.72px;
}
.mx{
    margin-left: 20px;
    margin-right: 20px;
  }
.wrapper-nav {
  max-width: 830px;
  width: 100%;
  height: 71px;
  box-shadow: 0 22px 40px rgba(36, 35, 51, 0.45);
  border-radius: 15px;
  background-color: #242333;
  margin-right: 33px;
}
.nav-link {
  display: flex;
  text-decoration: none;
}
.nav-link span {
  color: #9d9acc;
  font-family: "Geomanist-Book";
  font-size: 14px;
  font-weight: 400;
  letter-spacing: 0.56px;
  transition: 0.3s;
}
.nav-link span:hover {
  color: white;
}
.nav-back-block {
  margin-right: 20px;
}
.nav-next-block {
  margin-left: 20px;
}
.content-nav {
  display: flex;
  justify-content: space-between;
  padding-left: 23px;
  padding-right: 23px;
  opacity: 0.8;
  line-height: 71px;
}
@media screen and (max-width: 991px) {
  .content {
    flex-direction: column;
    align-items: center;
  }
  .main-content {
    margin-right: 0;
  }
}
@media screen and (max-width: 575px) {
  .comments-header-right {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
  .active {
    border-bottom: none;
  }
  .com-btn {
    padding-bottom: 15px;
    margin-left: 0;
    padding-left: 0;
  }
  .comments-header{
    flex-direction: column;
  }
  .comments-header-right{
    margin-top: 10px;
    align-items: flex-start;
  }
  .comment-view{
    flex-direction: column;
    align-items: center;
  }
  .comment-user-icon{
    margin-right: 0;
    margin-bottom: 15px;
  }
  .u-name{
    text-align: center;
  }
  .likes{
    margin-right: 30px;
  }
  .record-footer{
    flex-direction: column;
    align-items: center;
  }
  .footer-comment{
    margin-bottom: 10px;
  }
  
  .nav-next-block{
    margin-left: 10px;
  }
  .nav-back-block{
    margin-right: 10px;
  }
}
</style>
