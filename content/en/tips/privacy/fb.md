---
title: "Reset Facebook AD tracking / 重設 Facebbook 廣告追蹤"
date: "2018-07-06"
---

##### 你的廣告偏好 
* 用來移除『你近期最常查看的廣告商』
* https://www.facebook.com/adpreferences/advertisers/

```js
// 在瀏覽器的 Console 中執行以下指令可以把該頁顯示的隱藏，所以需要一直手動重新整理。記得 Facebook 要是使用繁體中文版
document.querySelectorAll("[aria-label=隱藏廣告]").forEach(e=>e.click());
```


</br>


##### 你的廣告偏好 
* 用來移除『你的興趣』
* https://www.facebook.com/adpreferences/?entry_product=waist&section=interests

```js
// 在瀏覽器的 Console 中執行以下指令可以一次把『你的興趣』全數移除。記得 Facebook 要是使用繁體中文版
document.querySelectorAll("[aria-label=移除]").forEach((e, idx)=>{setTimeout(()=>e.click(), idx*1000)})
```

</br>

##### Facebook 站外動態
* 清除或是關閉後可以避免商家和組織與 Facebook 分享有關我們與其互動的資訊
* 但這同時會影響到使用 Facebook 登入的第三方服務
* https://www.facebook.com/off_facebook_activity/?entry_point=1

