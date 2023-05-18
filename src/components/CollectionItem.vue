<template>
  <div class="collectionItem flex justify-between">
    <div>
      <div class="flex align-start">
        <img :src="bookmarkIcon" class="bookmark"/>
        <p>APPX System New Version Release Announce on  14th Dec...</p>
      </div>
      <div class="flex action">
        <div class="flex">
          <img :src="likeIcon"/>
          <span>150 Likes</span>
        </div>
        <div class="flex">
          <img :src="commentIcon"/>
          <span>10 Comments</span>
        </div>
         <div class="flex">
          <img :src="shareIcon"/>
          <span>5 Shares</span>
        </div>
      </div>
    </div>
    <div class="mark-right">
      <p class="tag">News</p>
      <p class="date">Dec 19, 2022</p>
    </div>
  </div>
</template>

<script>
import bookmarkIcon from '../assets/icon/bookmark.svg'
import commentIcon from '../assets/icon/comment.svg'
import shareIcon from '../assets/icon/share.svg'
import likeIcon from '../assets/icon/like.svg'

export default {
  data() {
    return {
      bookmarkIcon,
      commentIcon,
      shareIcon,
      likeIcon
    }
  }
}
</script>

<style lang="scss" scoped>
.collectionItem {
  background-color: #fff;
  border: 1px solid #D5D5DA;
  padding: 15px;
  p {
    margin-top: 0px
  }
}
.align-start {
  align-items: start;
}
.bookmark {
  margin-right: 20px;
  cursor: pointer;
}
.action {
  margin-left: 35px;
  margin-top: 6px;
  div {
    margin-right: 20px;
    cursor: pointer;
    img {
      margin-right: 5px;
    }
    span {
      white-space: nowrap;
    }
  }
}
@media (max-width:720px) {
  .action {
    flex-direction: column;
    div {
      margin-bottom: 8px;
    }
  }
}
.mark-right {
  display: flex;
  flex-direction: column;
  align-items: end;
  justify-content: center;
}
.tag {
  font-size: 14px;
  color:#11263C;
  background-color: #EDEDED;
  padding: 5px;
  border-radius: 50px;
  width: 49px;
  text-align: center;
  margin: 0px;
  margin-right: 0px;
  margin-bottom: 10px;
}
.date {
  color: #737791;
  font-size: 14px;
}
</style>