# TaiwanCalendar

[![jsDelivr ruyut/TaiwanCalendar/badge)](https://data.jsdelivr.com/v1/package/gh/ruyut/TaiwanCalendar/badge)](https://www.jsdelivr.com/package/gh/ruyut/TaiwanCalendar)

紀錄中華民國政府行政機關辦公日曆表的 JSON 資料，內容包含日期、星期、是否放假、說明。

## 關於

此資料來源為政府資料開放平台中的[中華民國政府行政機關辦公日曆表](https://data.gov.tw/dataset/14718)
，但在使用原始資料時遇到下列幾點問題：

* 以 Big5 編碼
* 轉碼後鍵值對應的 Key 的部分為中文
* 放假與否的值為 `"0"` 和 `"2"`
* 各年份連結無關聯，不易查詢不同年份的資料

故將資料整理後開源

## 資料取用連結

CDN 連結 (需要替換年份):

```
https://cdn.jsdelivr.net/gh/ruyut/TaiwanCalendar/data/{year}.json
```

2023 年度資料連結:

```
https://cdn.jsdelivr.net/gh/ruyut/TaiwanCalendar/data/2023.json
```

## 資料格式

資料以 JSON 格式儲存，內容如下:

```json
[
  {
    "date": "20230101",
    "week": "日",
    "isHoliday": true,
    "description": "開國紀念日"
  },
  {
    "date": "20230102",
    "week": "一",
    "isHoliday": true,
    "description": "補假"
  },
  {
    "date": "20230103",
    "week": "二",
    "isHoliday": false,
    "description": ""
  }
]
```

## 資料更新

目前中華民國政府行政機關辦公日曆表更新日期約為每年 6 月份更新下一年度的資料，故待原始資料更新後，此處資料將會盡可能的同步更新。

## 已知問題

因僅調整格式，未更改 `description` 資料內容，故無法直接使用 `description` 資料內容判斷，2017 ~ 2020 年補班的說明為 `調整上班`，但 2021 ~ 2023
年的說明為 `補行上班`。且 2023 年的說明還有包含 `小年夜`

目前已出現過的內容為: 開國紀念日, 補假, 小年夜, 農曆除夕, 春節, 調整上班, 補行上班, 調整放假, 放假, 和平紀念日, 兒童節及民族掃墓節, 兒童節,
民族掃墓節, 端午節, 中秋節, 國慶日

## 授權

原始資料使用[政府資料開放授權條款-第1版](https://data.gov.tw/license)
授權，依照第三條第二項要求標示出處為[政府資料開放平台](https://data.gov.tw/)，且依第四條第二項說明使用「創用CC授權 姓名標示 4.0 國際版本」授權釋出。

## 相關連結

* [中華民國政府行政機關辦公日曆表 JSON API 資料整理](https://www.ruyut.com/2022/08/Taiwan-calendar-api.html)