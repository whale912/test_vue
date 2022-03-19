<template>
  <div class="top-header"></div>
  <div class="menu-line"></div>
  <div class="container">
    <ul class="menu-bar">
      <li class="menu" v-for="menu in menuList" v-bind:key="menu">{{ menu }}</li>
    </ul>

    <div v-for="main in mainList" v-bind:key="main" class="main-box">
      <div class="title-bar">
        <span class="title-text">{{ main }}</span>
        <button class="title-button">바로가기</button>
      </div>
      <div class="main-content">
        <grid :colModel="colModel" :gridData="gridData" :listSize="7"></grid>
      </div>
    </div>
  </div>
</template>

<script>

import grid from "@/components/grid";
export default {
  name: 'App',
  data() {
    return {
      menuList: [
          "홈", "팀소개", "선수소개", "뉴스", "일정", "공지", "이벤트", "게시판"
      ],
      mainList: ["공지사항", "이벤트", "일정", "게시판"],
      colModel: [
        {text: "번호", name: "rowIdx", width: "50px", align: "center"},
        {text: "제목", name: "title", width: "auto", align: "left"},
        {text: "작성자", name: "writer", width: "80px", align: "center"},
      ],
      gridData: [
        {rowIdx: 1, title: "제목1", writer: "이윤배1"},
        {rowIdx: 2, title: "제목2", writer: "이윤배2"},
        {rowIdx: 3, title: "제목3", writer: "이윤배3"},
        {rowIdx: 4, title: "제목4", writer: "이윤배4"}
      ]
    }
  },
  components: {
    grid
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR&display=swap');

* { box-sizing: border-box; font-family: 'Noto Sans KR', sans-serif; }

html { margin: 0px; padding: 0px; }

body { height: 100%; margin: 0px; padding: 0px; }

.top-header {
  position: absolute; top: 0; width: 100%;height: 30px; background: black; z-index: -1;
}

.menu-line {
  position: absolute; top: 30px; width: 100%; height: 80px; background: #D29D25; z-index: -1;
}

.container {
  width: 1000px; height: 100%; margin: 0 auto;
}

.menu-bar {
  width: 100%; height: 80px; margin-top: 30px; padding:0;
  list-style: none; align-items: center; text-align: center;
}
.menu { display: inline-block; width: 100px; height: 80px; padding: 20px; line-height: 40px; cursor: pointer; }
.menu:hover { background: #956f1a }

.main-box {
  width: 500px;  height: 400px; padding: 10px; float: left;
}

.title-bar { width: 100%; height: 50px; align-items: center;}
.title-text { font-weight: bold; font-size: 1.17em; padding: 10px 0px 10px 0px; float: left; }
.title-button { padding: 10px 0px 10px 0px; float: right; }

.main-content { width: 100%; height: calc(100% - 50px); border: 1px solid #bfbfbf }
/*.board-table {
  border-collapse: collapse;
  width: 100%;

}
.board-table th {
  border-left: 1px solid #bfbfbf;
  border-right: 1px solid #bfbfbf;
  border-bottom: 1px solid #bfbfbf;
  height: 30px;
}

.board-table th:first-child {
  border-left: 0px;
}

.board-table th:last-child {
  border-right: 0px;
}

.board-table .tb_row td {
  border-left: 1px solid #bfbfbf;
  border-right: 1px solid #bfbfbf;
  border-bottom: 1px solid #bfbfbf;
  height: 30px
}

.board-table .tb_row td:first-child {
  border-left: 0px;
}
.board-table .tb_row td:last-child {
  border-right: 0px;
}
.border-bottom-zero {
  border-bottom: 0px;
}*/
</style>
