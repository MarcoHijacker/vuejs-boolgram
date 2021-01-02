<template>

    <div class="singlePost">
      <div class="postHead">
        <div class="postAuthor">
          <img v-bind:src="data.profile_picture" class="profilePicPost">
          <div v-text="data.profile_fullname" class="postOwner"></div>
        </div>
        <div class="postDots"><i class="fas fa-ellipsis-h"></i></div>
      </div>
      <img v-bind:src="data.post_image" class="postPic">
      <div class="postDetails">
        <div class="postReaction">
          <i class="far fa-heart"></i>
          <i class="far fa-comment"></i>
        </div>
        <div class="postLikes">
          <img v-bind:src="data.likes[0].profile_picture" alt="profLiked" class="profLiked">
          <span class="userLiked">
            Piace a <strong class="pointed">{{ data.likes[0].username }}</strong><strong v-show="data.likes.length > 1" class="pointed"> e {{ data.likes.length - 1 }} altri</strong>.
          </span>
        </div>
        <div class="postMsg">
          <div class="postIgnick" v-text="data.profile_name"></div>
          <div class="postText" v-text="data.post_text"></div>
        </div>

        <div class="postComments" v-for="(comment, i) in displayComments" :key="`co${i}`">
          <span class="userComment">{{ comment.username }}</span>
          <span class="textComment">{{ comment.text }}</span>
        </div>

        <div class="toggleComments" v-if="data.comments.length > 3" @click="showMore.status = !showMore.status">{{ btnMore }} altri {{ data.comments.length -3 }} commenti</div>
        <div class="postDate">
          {{ showTime }} Ore fa
        </div>
        <div class="addComment">
          <input class="fillText" type="text" name="addComment" value="" placeholder="Aggiungi un commento...">
          <a href='#' class="comment">Commenta</a>
        </div>
      </div>
    </div>

</template>

<script>

export default {
    props: {
        data: {
            type: Object,
            required: true
        }
    },
    data: () => ({
        showMore: {
            status: false,
            limit: 3
        }
    }),
    computed: {
        displayComments() {
           return this.showMore.status ? this.data.comments : this.data.comments.slice(0, 3);
        },
        showTime() {
            var myFullDate = this.data.date.date;
            var myPartDate = myFullDate.split(" ");

            var myOnlyDate = myPartDate[0];
            var myHourDate = myPartDate[1];

            var updatedDate = myOnlyDate.split("-");
            var updatedHour = myHourDate.split(":");

            var parsedDate = new Date(updatedDate[0], updatedDate[1] - 1, updatedDate[2], updatedHour[0], updatedHour[1]);
            var todayDate = new Date();

            var todayDateMs = todayDate.getTime();
            var apiDateMs = parsedDate.getTime();

            var hourPassedMs = todayDateMs - apiDateMs;
            var hourPassed = Math.floor(hourPassedMs / 3600000);

            return hourPassed;
        },
        btnMore() {
            return this.showMore.status ? "Nascondi" : "Mostra";
        }
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

@media only screen and (max-width: 1300px) {
  .singlePost {
    margin-right: 0 !important;
  }
}
div.singlePost {
  padding: 0;
  background-color: white;
  border: solid 2px #e9e9e9;
  border-radius: 2px;
  margin-right: 30px;
  margin-top: 50px;
  img.profilePicPost {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    padding: 2px;
    border: solid 3px #d55761;
    margin-right: 8px;
    cursor: pointer;
  }
  div.postHead {
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    div.postAuthor {
      display: flex;
      align-items: center;
    }
    div.postOwner {
      font-size: 16px;
      font-weight: bold;
    }
    div.postDots {
      cursor: pointer;
    }
  }
  img.postPic {
    width: 100%;
    height: auto;
  }
  div.postDetails {
    padding: 20px;
    div.postLikes {
      display: flex;
      align-items: center;
      margin-top: 20px;
      font-size: 13px;
      img.profLiked {
        width: 24px;
        height: 24px;
        border-radius: 50%;
        margin-right: 8px;
        cursor: pointer;
      }
      span.userLiked {
        strong.pointed {
          cursor: pointer;
        }
      }
    }
    div.postComments {
      display: flex;
      margin-top: 10px;
      span.userComment {
        font-size: 13px;
        font-weight: bold;
        margin-right: 8px;
      }
      span.textComment {
        font-size: 13px;
      }
    }
    div.toggleComments {
      text-align: left;
      font-size: 13px;
      color: darkgrey;
      text-decoration: underline;
      cursor: pointer;
      text-align: left;
      margin-top: 10px;
    }
    div.postDate {
      display: flex;
      font-size: 13px;
      color: darkgrey;
      margin-top: 20px;
      font-weight: bold;
    }
    div.addComment {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
      border-top: solid 1px #cecece;
      padding-top: 10px;
      input.fillText {
        width: 70%;
        border: none;
        padding: 10px;
      }
      a.comment {
        text-decoration: none;
        color: #7bbaf7;
        font-size: 13px;
        font-weight: bolder;
        padding: 10px;
        &:hover {
          color: #547ea7;
        }
      }
    }
    div.postMsg {
      display: flex;
      margin: 10px 0 25px 0;
      div.postIgnick {
        font-size: 13px;
        font-weight: bolder;
      }
      div.postText {
        font-size: 13px;
        margin-left: 7px;
      }
    }
  }
  div.postReaction {
    font-size: 32px;
    text-align: left;
    i {
      margin: 0 10px;
      cursor: pointer;
      &:hover {
        color: rgb(238, 39, 87);
      }
    }
  }
}

</style>
