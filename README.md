
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>美麗媽的秘製食譜</title>
<style>
body {
font-family: "微軟正黑體", sans-serif;
background: #e6f5e6; /* 淡綠色背景 */
margin: 0;
padding: 20px;
color: #333;
}
h1 {
text-align: center;
color: #8a4fff; /* 紫色標題 */
}
.buttons {
text-align: center;
margin-bottom: 20px;
}
.buttons button {
background: #bfa5ff; /* 淺紫色按鈕 */
border: none;
padding: 10px 20px;
margin: 5px;
font-size: 16px;
cursor: pointer;
border-radius: 5px;
transition: background 0.3s;
color: white;
}
.buttons button:hover {
background: #a084e8;
}
.search-container {
text-align: center;
margin-bottom: 20px;
}
#searchInput {
width: 60%;
padding: 10px;
font-size: 16px;
border-radius: 8px;
border: 1px solid #ccc;
}
.recipe {
background: #f5fff5; /* 更亮一點的綠白色卡片 */
border: 2px solid #bfa5ff; /* 淺紫色邊框 */
border-radius: 10px;
padding: 15px;
margin: 10px auto;
max-width: 600px;
box-shadow: 2px 2px 10px rgba(0,0,0,0.1);
}
.recipe h2 {
margin-top: 0;
color: #8a4fff; /* 紫色小標題 */
}
.section-title {
font-weight: bold;
margin-top: 10px;
color: #6a5acd; /* 稍微深一點的紫色 */
}
</style>
</head>
<body>

<h1>美麗媽的秘製食譜</h1>

<!-- 搜尋欄位 -->
<div class="search-container">
<input type="text" id="searchInput" placeholder="搜尋食譜...">
</div>

<!-- 分類按鈕 -->
<div class="buttons">
<button onclick="filterRecipes('全部')">全部</button>
<button onclick="filterRecipes('家常菜')">家常菜</button>
<button onclick="filterRecipes('甜點')">甜點</button>
<button onclick="filterRecipes('麵包／早餐')">麵包／早餐</button>
<button onclick="filterRecipes('鹹的')">鹹的</button>
<button onclick="filterRecipes('肉類')">肉類</button>
<button onclick="filterRecipes('其他')">其他</button>
</div>

<!-- 食譜內容 -->
<div id="recipes">
<div class="recipe" data-category="家常菜 肉類">
<h2>香煎雞腿排</h2>
<div class="section-title">食材：</div>
<ul>
<li>去骨雞腿排 2片</li>
<li>鹽 少許</li>
<li>黑胡椒 少許</li>
<li>橄欖油 1大匙</li>
</ul>
<div class="section-title">步驟：</div>
<ol>
<li>雞腿排用鹽和黑胡椒均勻醃10分鐘。</li>
<li>平底鍋加熱，放入橄欖油。</li>
<li>雞皮朝下小火煎至金黃，再翻面煎熟即可。</li>
</ol>
</div>

<div class="recipe" data-category="甜點 其他">
<h2>蜂蜜檸檬果凍</h2>
<div class="section-title">食材：</div>
<ul>
<li>檸檬汁 50ml</li>
<li>蜂蜜 3大匙</li>
<li>吉利丁粉 10g</li>
<li>水 300ml</li>
</ul>
<div class="section-title">步驟：</div>
<ol>
<li>將水加熱至溫暖，加入吉利丁粉攪拌溶解。</li>
<li>拌入蜂蜜與檸檬汁。</li>
<li>倒入模具中，冷藏4小時至凝固。</li>
</ol>
</div>

<div class="recipe" data-category="麵包／早餐 甜點">
<h2>鬆餅</h2>
<div class="section-title">食材：</div>
<ul>
<li>低筋麵粉 200g</li>
<li>牛奶 150ml</li>
<li>蛋 1顆</li>
<li>砂糖 2大匙</li>
<li>泡打粉 1小匙</li>
</ul>
<div class="section-title">步驟：</div>
<ol>
<li>將所有材料攪拌均勻成麵糊。</li>
<li>平底鍋加熱後，小火煎至兩面金黃。</li>
<li>可依喜好搭配果醬或蜂蜜食用。</li>
</ol>
</div>
</div>

<!-- 功能腳本 -->
<script>
function filterRecipes(category) {
var recipes = document.getElementsByClassName('recipe');
for (var i = 0; i < recipes.length; i++) {
if (category === '全部') {
recipes[i].style.display = 'block';
} else {
if (recipes[i].getAttribute('data-category').includes(category)) {
recipes[i].style.display = 'block';
} else {
recipes[i].style.display = 'none';
}
}
}
}

// 搜尋功能
document.getElementById('searchInput').addEventListener('input', function() {
var searchText = this.value.toLowerCase();
var recipes = document.getElementsByClassName('recipe');
for (var i = 0; i < recipes.length; i++) {
var content = recipes[i].innerText.toLowerCase();
if (content.includes(searchText)) {
recipes[i].style.display = 'block';
} else {
recipes[i].style.display = 'none';
}
}
});
</script>

</body>
</html>
