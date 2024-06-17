---
Title: WCM 五專第7週課程內容
Date: 2024-05-18 16:12
Category: 五專
Tags: , w7
Slug: wcm-5j-w7
Author: 51233116
---


<!-- PELICAN_END_SUMMARY -->
# 練習利用程式建立單字查詢網頁
利用 Python 建立 Javascript 電子書的單字查詢超文件
利用 [2.txt](https://mde.tw/wcm2024/downloads/2.txt) 與 [1.txt](https://mde.tw/wcm2024/downloads/1.txt) Python 程式, 從下列電子書建立英文單字查詢網頁

# Brython 程式
Brython 是一種在瀏覽器中運行的 Python 解譯器。它允許您在網頁上使用 Python 來編寫 Web-based 前端程式，而無需安裝任何套件或外部解譯器。

# 舉一個簡單 Brython 程式範例, 從 1 累加到 10, 然後在網頁中以 html 列出運算結果

<!-- 導入 Brython 程式庫 -->
<script src="./../cmsimde/static/brython.js"></script>
<script src="./../cmsimde/static/brython_stdlib.js"></script>
<!-- 啟動 Brython -->
<script>
window.onload=function(){
brython();
}
</script>
<h1>累加結果：</h1>
<!-- 顯示結果標註 -->
<ul id="result"></ul>

<!-- 在 <script type="text/python"> 標籤中編寫 Python 代碼 -->
<script type="text/python">
from browser import document
result_list = document.getElementById("result")
# sum 初始值設為 0
sum = 0
init = 1
upto = 10
# 利用 for 重複迴圈與變數加法進行累加
for i in range(init, upto+1):
sum = sum + i
# skip the first one
if i !=1:
result_list.innerHTML += "<li>{} + {} = {}</li>".format(sum-i, i, sum)
</script>