# Calyx API 文件使用說明

Calyx API 可以讓開發者或是第三方服務商快速方便地整合 Calxy 產品相關資訊至他們的產品或服務裡。

Calyx API 文件使用 Swagger 做為模版，而這份文件是為了讓第一次使用 Swagger Doc 或是 Calyx API 的開發者可以快速上手使用 Calyx API 。

## 環境
目前 Calyx 有兩個系統環境一個是 [stage](https://test.calyxtechs.com/api-docs) ，一個是 [production](https://dashboard.calyxtechs.com/api-docs) 。

如果您已經有 Calyx 產品正在測試，Calyx 公司創建給您的帳戶資料是在 production 。這部份已有討論之後會建立 play ground 或沙盒環境。目前請先使用 production 環境測試您的產品。

## 使用說明
打開 [Calyx API](https://dashboard.calyxtechs.com/api-docs)

### 確認環境

使用環境需與選擇的 server 相符。
![check server](https://user-images.githubusercontent.com/84309449/140894896-c5b6b53b-d664-47f4-8a0b-d33f22af1723.jpg)

### 首次登入
1. 點選 Auth 區塊理的 `POST /auth/signin`
![select signin](https://user-images.githubusercontent.com/84309449/140895030-ae0c3112-714c-4773-b717-2aeb2694bc9f.jpg)
2. 展開後，點選 Try it out
![try it out](https://user-images.githubusercontent.com/84309449/140895225-3a6065e3-f5d0-4fcb-9561-09b770076401.jpg)
3. 在 Request body 修改您的帳號密碼，點選 execute
![input pw and execute](https://user-images.githubusercontent.com/84309449/140895503-1db23d1b-fe08-46e9-86c8-788add63be24.jpg)
4. 您將會在 Respond body 裡收到帳號相關資訊，其中 token 以及 companyId 接著會用到
![signin result](https://user-images.githubusercontent.com/84309449/140895883-4c18c966-f5b8-47bd-bfa9-ee7967576274.jpg)

### Authorize
幾乎每隻 Calxy API 都會檢查使用者權限，所以在呼叫時， request header 都需要設定 token 讓 Calyx 系統知道這次訪問的使用者身分。
Swagger Doc 的功能之一，就是只要授權一次，之後的 API 呼叫都會自動帶上您設定好的 token 。
1. 點選 Authorize
![select autorize](https://user-images.githubusercontent.com/84309449/140897243-1f699d12-f6b9-4a4e-9e87-a5de9077dc5e.jpg)
2. 填入時拿到的 token ，點選 Authorize 。
![authorize](https://user-images.githubusercontent.com/84309449/140898210-2aac82ed-ab32-44f0-95c9-05480eb86624.jpg)

### 取得 Sensing Data
1. 點選 Position 區塊裡的 `GET /{CompanyId}/positions`
![Select poistions API](https://user-images.githubusercontent.com/84309449/140900912-2168bfe6-1c11-4bd2-bd1f-b99ab0036028.jpg)
2. 點選 Try it out
![position try it out](https://user-images.githubusercontent.com/84309449/140901015-c268d4a5-19ed-4144-b64f-57d1441cce75.jpg)
3. 更改 companyId 後，點選 Execute
![call position api](https://user-images.githubusercontent.com/84309449/140903467-c87e7de9-1c4f-4897-9015-b9c298fa7e3d.jpg)
4. 您就可以在 respond body 拿到每個 position 即時的 sensing data
![sensing data](https://user-images.githubusercontent.com/84309449/140904599-b030422e-6b67-4660-a7cd-1bb37f61dcd9.jpg)


