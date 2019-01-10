<template>
  <div id="app">
    <my-sidebar class="sidebar"></my-sidebar>
    <my-content class="content"></my-content>
  </div>
</template>

<script>
import MySidebar from "./components/MySidebar.vue"
import MyContent from "./components/MyContent.vue"
export default {
  name: "app",
  data() {
    return {   
    };
  },
  components:{
    MySidebar,
    MyContent
  }
};
</script>

<style>
/* сброс стилей браузера */
html, body, div, span, object, iframe, h1, h2, h3, h4, h5, h6, p, blockquote, pre, a, abbr, acronym, address, big, cite, code, del, dfn, em, img, ins, kbd, q, s, samp,small, strike, strong, sub, sup, tt, var, b, u, i, center, dl, dt, dd, ol, ul, li, fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td, article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	vertical-align: baseline;
}
article, aside, details, figcaption, figure, footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1.2;
}
ol { 
	padding-left: 1.4em;
	list-style: decimal;
}
ul {
	padding-left: 1.4em;
	list-style: square;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
} 
/* конец кода сброса стилей браузера */

#app {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
}
.sidebar {
  flex: 0 0 300px;
}
.content {
  flex: 1 0 300px;
}
</style>


