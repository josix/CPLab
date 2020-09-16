---
marp: true
theme: default
paginate: true
---

<style>

section {
    font-family: 微軟正黑體
}

</style>

# Assignment 新增流程
    1. Create Problem 
    2. Create Contest
    3. 將題目匯入 Contest

---
# Create Problem
## 路徑
    1. 點擊右上方帳號下方的連結 Manaegment 進入管理頁面
    2. 在左方的 Problem 標籤底下選擇Create Problem 
    3. 進入新增題目頁面

---
# Create Problem
## 說明
*   Display ID 設定題目 ID, **ID 不會自動排序**, 也**不能重複**, 但**可以輸入空白以及中英文**
*   Title 設定題目標題, 同樣**可以輸入中英文及空白**
*   Description 設定題目敘述
*   Input & Output Description 說明輸入及輸出
*   Visible 預設開啟, **請將其取消**, 待課程結束後統一上線
*   Tag 統一使用 **1091CP1**
*   Language 只勾選 C ,**其他語言請取消**
*   Input & Output Samples 為輸入及輸出範例

---
# Create Problem
## 測資
*   測資類型分為 ACM 及 OI 兩種, **CP1請選 OI 制**, 題目配分可在測資上傳後作設定
*   一組測資檔必須有 .in 檔 & .out 檔
*   測資檔命名須按照 1、2、3 等順序以此類推。如: 1.in 1.out 2.in 2.out ...
*   測資請全部打成一包後壓縮上傳, 壓縮格式必須為 zip 檔, 以上若有任何一步出錯, 測資便無法佈署
*   [可以參考這裡](https://docs.onlinejudge.me/#/onlinejudge/guide/test_case) 

---
# Create Contest
## 路徑
*   Management > Contest > Create Contest
## 說明
*   Title 設定為 Assignment X, X 為當次作業
*   Description 設定 Assignment X 繳交區, X 為當次作業
*   Start & End Time 設定起訖時間
*   Contest Rule Type **必須選擇 OI** 否則題目無法引入
*   status 可設定競賽可見與否

---
# 將題目匯入 Contest
## 路徑
*   Management > Contest > Contest List > 找到你剛剛創建的競賽
*   點下右邊數來第三個方框 Problem
## 匯入題目
*   在 Contest Problem List 最下方點擊 ```Add From Public Problem```
*   找到你剛剛創建的題目後, 按下右方 + 就完成創建了!




