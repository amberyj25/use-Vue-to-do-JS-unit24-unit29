<template>
    <div class="wrap"> 
        <router-link to="/">首頁</router-link>
        <router-link :to="{name:'eat'}">在計算消費的頁面</router-link>
		<div class="content">
			<div class="content-inner">
				<h2>六角西餐廳-顧客點餐篇</h2>
				<p>服務生 ： Hello，請問您想要點什麼？</p>
				<p>顧客 ： 給我<input type="text" v-model="humber">個漢堡，再<input type="text" v-model="drink">杯可樂吧！</p>
                <p>服務生 ： <button type="button" @click="button1">計算</button>，好的，總計是{{total}}元</p>
			</div>
		</div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            humber:"",
            drink:"",
            total:""
        }
    },
    methods:{
        button1(){
            if(this.humbe =="" || this.drink == ""){return};
            const humbernumber = parseInt(this.humber);
            const drinknumber = parseInt(this.drink);
            this.total= humbernumber*100+drinknumber*20;
        }
    }
}
</script>
<style scoped>
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
.wrap{
    width: 1000px;
    height: 1000px;
    margin: auto;
    background: url("./img/desktop.png") no-repeat  200px  100px;
	position: relative;
}
.content{
	width: 700px;
	height: 250px;
	position: absolute ;
	left: 250px;
	top: 200px;
	color: yellow;
	font-size: 25px;
	background: #000;
	opacity:.7;
}
.content h2{
	font-size: 40px;
	margin-bottom: 10px;
}
.content-inner{
	width: 700px;
	height: 250px;
	margin-top: 20px;
	margin-left:125px;
}
.content-inner p{
	margin-bottom: 10px;
}
input[type="text"]{
	width: 50px;
	height: 20px;
}
</style>