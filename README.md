# TANetRoamer-units
各校 TANet Roaming 的設定檔，用在其他平台(Desktop、Android...)的產品上。

## 開發

### units.json

這個檔案是各校的設定檔，id 與 name 都已經準備好，就只差 url 與 data，url 為各校 WIFI 登入的 API 網址，data 則是傳送給 API 的資料，其中值為 %u 與 %p 的皆會被使用者設定的帳號與密碼取代。

 若有學校的登入流程複雜或特殊，請[開 issue](issue/new) 討論是否更改程式結構。

```javascript
[{
  "id" : "0015", // 學校代碼，依照 https://ulist.moe.gov.tw/ 公布資訊為主
  "name" : "國立彰化師範大學", // 學校名稱
  "realm": "mail.ncue.edu.tw", // realm，通常為學生信箱網域。
  "url" : "http://securelogin.arubanetworks.com/auth/index.html/u", // 登入 API 網址，有可能視學校而有所不同。
  "data" : { // 送 API 的資料，視學校 API 而有所不同，此為彰師大設定。
    "user_foo" : "%u", // 值為 '%u'，指的是帳號
    "password_foo" : "%p", // 值為 '%p'，指的是密碼
    "foo" : "bar",
    "foo2" : "bar2"
  }
}]
```
