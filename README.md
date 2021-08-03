# Cathay Bank - Vue.js

## HeroKu deploy server

> 第一次開啟需要稍等伺服器回應

[https://cathay-bank-vue.herokuapp.com/](https://cathay-bank-vue.herokuapp.com/)

---

### Project introduce

1. 首頁點擊 "**立即購服務登錄**" 或網頁右上方 "**立即購**"，即跳轉至登錄畫面。
1. 使用者輸入身分證後5碼、信用卡號、生日以及驗證碼。
1. 勾選 "**本人已閱讀並同意上述共同行銷條款**"。
1. 確認資料輸入完畢，即可點擊 "**確認送出**"。

---

### Fool-proof design

| input | limit | type | verify |
|-|:-:|:-:|:-:|
| last 5 number of ID | 5 | number | ✅ |
| card number | 4 | number | ✅ |
| birth | 8 | number | ✅ |  
| captcha| - | text | ✅ |  

---

### Color code

#### *background-color*

| Hex | html-tag |
|-|:-:|
|<span style="color:#39b565">◼︎</span> #39b565|`navbar`|
|<span style="color:#65bd44">◼︎</span> #65bd44|`banner`|
|<span style="color:#f2f2f2">◼︎</span> #f2f2f2|`copyright`|
|<span style="color:#fafafa">◼︎</span> #fafafa|`footer`|

#### *font-color*

|Hex|font-weight|
|-|:-:|
|<span style="color:#4a4a4a">◼︎</span> #4a4a4a|`regular`|
|<span style="color:#a4a4a4">◼︎</span> #a4a4a4|`light`|

#### *Other*

|Hex|element-type|
|-|:-:|
|<span style="color:#ff6200">◼︎</span> #ff6200|`button`|
|<span style="color:#6d6d6d">◼︎</span> #6d6d6d|`back-to-top`|
