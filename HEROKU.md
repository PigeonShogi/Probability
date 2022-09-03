# HEROKU 上傳指引
## 前言
本檔案只列出部分步驟，若要從零開始使用 HEROKU，可參考 AC 教案。
```
https://lighthouse.alphacamp.co/courses/118/units/25466
https://lighthouse.alphacamp.co/courses/100/units/20933
```
* 先用命令提示字元輸入 heroku login，完成後再改用 Git Bush 執行後續步驟。
* 在 HEROKU 網站上建立新專案，或者用 Git Bush 輸入指令：heroku create（補充：見下一步）
* 上一步驟也可於指令後方輸入自訂 APP 名稱。例：heroku create cute-animals
* HEROKU 網站上選取新建的專案，點選 Settings -> Reveal Config vars
* 將本地端 .env 裡的所有環境變數及參數輸入 HEROKU 後台，如下一項的範例：
* KEY 欄位輸入：MONGODB_URI VALUE 欄位輸入：mongodb+srv...
* 本地專案資料夾建立新檔案：Procfile
（如果 package.json 腳本有「 "start": "node app.js"」，本步驟與下一步驟似乎可省略。）
* Procfile 裡面寫入以下指令：web: node app.js
* 先確認 git 遠端清單是否含有 HEROKU：git remote -v
* 承上，若不含有 HEROKU 則輸入指令新增位址：git remote add heroku [heroku_git_url]
	例：git remote add heroku https://git.heroku.com/accounting-animal.git
* 建立 git commit：git add .
* 建立 git commit：git commit -m "chore: heroku init"
* git push heroku main
* 上傳後如果無法順利執行，可以先試著用 Git Bush 執行種子檔：heroku run npm run seed
