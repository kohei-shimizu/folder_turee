<template>
  <div>
    <div v-on:contextmenu.prevent="$refs.menu.open">
      <v-treeview :items="items" item-key="name" open-on-click></v-treeview>
    </div>
    <context-menu ref="menu">
      <li v-on:click="trash_empty()">text1</li>
      <li>text2</li>
      <li>text3</li>
      <li>text4</li>
      <li>text5</li>
    </context-menu>
  </div>
</template>

<script>
import Vue from "vue";
import Vuetify from "vuetify";
import "vuetify/dist/vuetify.min.css";
import contextMenu from "vue-context-menu";
Vue.use(Vuetify);
Vue.use(contextMenu);
export default {
  data: () => ({
    items: [
      {
        id: 1,
        name: "A",
        children: [
          {
            id: 2,
            name: "フルーツ",
            children: [
              { id: 3, name: "リンゴ" },
              { id: 4, name: "バナナ" },
              { id: 5, name: "オレンジ" },
            ],
          },
          {
            id: 6,
            name: "野菜",
            children: [
              { id: 7, name: "ジャガイモ" },
              { id: 8, name: "ニンジン" },
              { id: 9, name: "玉ねぎ" },
            ],
          },
        ],
      },
    ],
  }),
};
</script>

<style>
</style>
