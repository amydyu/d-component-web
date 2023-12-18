# 可用模塊 ( 文章 )
( 右側有選單可以快速轉跳 )
- title：標題
- min-title：副標題
- text：文字 / 可加連結
- list：清單 / 可加連結
- iframe：內嵌框架
- pdf：文件檔
- img：圖片
- sdgs：sDGS縮圖
- video：影片
- hr：分界線
- nullData：空一行
  
進階：
- twoObjects：版面對切，左右可放資料
- swapTextAndImg：版面對切，偶數調換

其他：
- 日誌、自主學習內容

## title 標題
- 一般大標題。
```
{
    "componentType": "title",
    "data": "這裡輸入標題名稱"
}

```
## min-title　副標題
- 一般副標題（小標題）。
```
{
    "componentType": "min-title",
    "data": "副標題名稱"
}
```
## text　文字
- 純文字 
- data陣列多筆文字，內容
```
{
    "componentType": "text",
    "data":[
            {
                "text": "第一行內容"
            },
            {
                "text": "第二行內容"
            }
        ]
}
```

- 帶有【連結】的text
```
{
    "componentType": "text",
    "data":[
            {
                "text": "如果中間有【畫面上顯示的名稱】會顯示在中間，如果沒有會加在最後面。",
                "link":{
                    "text": "畫面上顯示的名稱",
                    "fileName": "檔案實際名稱",
                    "link":"learn/directions/learnDirections01.pdf"
                }
            },
            {
                "text": "第二行內容"
            }
        ]
}

```

##  list 清單
- type : 可設定ul & ol 
- data : 內容
- text : 內容文字
- text - data : 若有第二層再輸入
```
{
    "componentType": "list",
    "data": {
        "type": "ul",
        "style": "",
        "data": [
            {
                "text": "第一階層第一行，每一層都可加連結",
                "data": {
                    "type": "ol",
                    "data": [
                        {
                            "text": "第二階層第一行"
                        },
                        {
                            "text": "第二階層第二行",
                            "data": {
                                "type": "ul",
                                "data": [
                                    {
                                        "text": "第三階層第一行"
                                    },
                                    {
                                        "text": "第三階層二行",
                                        "link":{
                                            "text": "顯示的連結名稱",
                                            "fileName": "檔案的連結名稱",
                                            "link":"文件檔案名稱"
                                        }
                                    }
                                ]
                            }
                        }
                    ]
                }
            },
            {
                "text": "第一階層第二行",
                "data": {
                    "type": "ol",
                    "data": [
                        {
                            "text": "第二階層第一行"
                        },
                        {
                            "text": "第二階層第二行"
                        }
                    ]
                }
            }
        ]
    }
}

```

- list的連結：
```
"link":{
    "text": "畫面上顯示的名稱",
    "fileName": "檔案實際名稱",
    "link":"learn/directions/learnDirections01.pdf"
}
```

- list的 2~3 階層：
```
"data": {
    "type": "ol",
    "data": [
        {
            "text": "第二階層第一行"
        },
        {
            "text": "第二階層第二行"
        }
    ]
}
```

## iframe
- title:影片名稱(為了符合無障礙網站，需描述內容名稱)
- width:顯示在畫面上的寬度
- height:顯示在畫面上的高度
```
{
    "componentType":"iframe",
    "data":{
        "link":"https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3644.9029544648097!2d120.59252571498607!3d23.999203784467365!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x34693768664f3ccb%3A0xe8c679292eeb5326!2zNTE15b2w5YyW57ij5aSn5p2R6YSJ5a245bqc6LevMTY46Jmf!5e0!3m2!1szh-TW!2stw!4v1509635572296",
        "title":"【老王說】夜路走多了總會碰到鬼-半夜被叫名字為何不能回頭？真人真事鬼故事",
        "width":"100%",
        "height":"300px"
    }
},
```
## pdf
- 網頁上顯示pdf
- title:檔案名稱(為了符合無障礙網站，需描述內容名稱)
- width:顯示在畫面上的寬度
- height:顯示在畫面上的高度
```
{
    "componentType":"pdf",
    "data":{
        "title":"名稱",
        "link":"在files資料夾底下的檔案，如果有其他資料夾階層，請補上，檔案名稱包含副檔名（小寫）",
        "width":"100%",
        "height":"700px"
    }
}

```

## img 圖片 / 多張圖片
- data陣列為多筆圖片，如圖片兩張以上顯示方式為　【輪播】　樣式。
- cols :網頁版的圖片顯示大小為畫面的８／１２　（只有單張圖片時適用）
- imgLink : 圖片路徑（請注意副檔名只能小寫）
- alt: 圖片名稱(為了符合無障礙網站，需描述圖片名稱)

```
{
    "componentType": "img",
    "cols": "8",
    "data":[
        {
            "imgLink":"organizationalChart.png",
            "alt": "學院組織圖"
        }
    ]
}
```
- 多張圖片寫法
```
{
    "componentType": "img",
    "data":[
        {
            "imgLink":"index/index-communicate.png",
            "alt": "請輸入圖片名稱"
        },
        {
            "imgLink":"index/index-digital.png",
            "alt": "請輸入圖片名稱"
        },
        {
            "imgLink":"index/index-STEAM.png",
            "alt": "請輸入圖片名稱"
        }
    ]
}
```

## sdgs
- alignment :當網頁版的時候，整體對齊的方向。
- cols :手機板，圖片顯示大小為畫面的 ３／１２
- cols_md :網頁版，圖片顯示大小為畫面的　２／１２
- data: sdgs對應的編號為?

```
{
    "componentType": "sdgs",
    "alignment": "right",
    "cols": "3",
    "cols_md": "2",
    "data":["04","06","07","13","15"]
}
```

## video 影片
- videoTitle:檔案名稱(為了符合無障礙網站，需描述內容名稱)
- width:顯示在畫面上的寬度
- height:顯示在畫面上的高度
```
{
    "componentType": "video",
    "data": {
        "videoTitle": "環境教育STEAM微學程宣傳影片",
        "videoLink": "https://www.youtube.com/embed/JJcJnfr3q8w?si=Pr3_8JG2_nJEWFmQ"
    }
}

```

## hr 分界線
- 網頁上顯示一條橫線
```
{
    "componentType": "hr"
}
```

## nullData 空一行
- 位畫面控一格
```
{
    "componentType": "nullData"
}

```

## twoObjects 版面對切，左右可放資料
- leftData：裡面可任意資料放 『上方的資料』 (非進階)
- rightData：裡面可任意資料放 『上方的資料』 (非進階)
```
{
  "componentType": "twoObjects",
  "leftData":[
      {
          "componentType": "img",
          "cols":"",
          "data":[
              {
                  "imgLink":"index/index-digital.png",
                  "alt": "數位科技與應用微學程形象圖案"
              }
          ]
      }
  ],
  "rightData":[
      {
          "componentType": "title",
          "data": "運用數位科技學習解決專業問題之能力"
      }
  ] 
}

```


## swapTextAndImg 版面對切，偶數調換
- contents：可以放多筆文字
```
{
    "componentType": "swapTextAndImg",
    "data":[
        {
            "imgLink":"圖片連結",
            "imgtitle":"圖片名稱(為了符合無障礙網站，需描述圖片名稱)",
            "title":"這是副標題",
            "contents":[
                {
                    "text":"這個是內容"
                }
            ],
            "link":"連結，沒有做外部連結，可以不要，但請勿任意調整"
        },
        {
            "imgLink":"圖片連結",
            "imgtitle":"圖片名稱(為了符合無障礙網站，需描述圖片名稱)",
            "title":"這是副標題",
            "contents":[
                {
                    "text":"這個是內容，可以放多筆文字，同text文字的data用法，不可超連結"
                }
            ],
            "link":"連結，沒有做外部連結，可以不要，但請勿任意調整"
        }
    ]
}

```


## 日誌、自主學習內容
- seq：自己填寫，只能增加，不可減少，特殊情況可以跳號，使用過的數字，請勿增加
- imgLink：封面圖片連結
- title：標題
- update：發表日期
- user_unit：發佈單位
- user：發佈人姓名
- content：自由編排內容，請參考上方【可用模塊】
```
{
    "seq": "1",
    "imgLink": "portfolio/certificate01.jpg",
    "title": "「2023法律法遵科技黑客松」初賽入選",
    "update": "2023-11-03",
    "user_unit": "校發處",
    "user": "黃莘扉",
    "content": [
        {
            "componentType": "text",
            "data":[
                {
                    "text": "資工系學生鄭翔瑋、林子喬"
                },
                {
                    "text": "參加『2023法律法遵科技黑客松』比賽，"
                },
                {
                    "text": "通過初賽前20名"
                }
            ]
        },
        {
            "componentType": "nullData"
        },
        {
            "componentType": "text",
            "data":[
                {
                    "text": "指導老師：資工系施倫閔老師、財金系賴奕豪老師"
                }
            ]
        }
    ]
}

```
