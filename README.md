# 【總筆記】目錄
###### tags: `catalog`

Copyright 2021, [月下麒麟 YMont](https://hackmd.io/@YMont/note-catalog)

---

## Open Source with C
**Project name: libmodbus**
* 2021.08 [如何看懂Open Source : 帶你閱讀一座程式I](https://hackmd.io/@YMont/c-libmodbus_I) 
* 2021.08 [如何看懂Open Source : 帶你閱讀一座程式II](https://hackmd.io/@YMont/c-libmodbus_II) 
* 2021.08 [如何看懂Open Source : 帶你閱讀一座程式III](https://hackmd.io/@YMont/c-libmodbus_III) 
* 2021.08 [如何看懂Open Source : 帶你閱讀一座程式IIIV](https://hackmd.io/@YMont/c-libmodbus_IIIV) 
* 2021.09 [附註 帶你閱讀一座程式 函式拆解I](https://hackmd.io/@YMont/c-libmodbus_function_I) 
* 2021.09 [附註 帶你閱讀一座程式 函式拆解II](https://hackmd.io/@YMont/c-libmodbus_function_II) 

## Website
**--Backend--**
**Python - FastAPI**
* 2021.11 [後端學習紀錄 Backend with FastAPI (1) - Setting Enviroment](https://hackmd.io/@YMont/python-fastapi-1)
* 2021.11 [後端學習紀錄 Backend with FastAPI (2) - Website with Departure](https://hackmd.io/@YMont/python-fastapi-2)
* 2021.11 [後端介接前端 Backend with FastAPI (3) - Through the Galaxy](https://hackmd.io/@YMont/python-fastapi-3)
* 2021.12 [FastAPI APIRoute() 應用實作 - Route in Large System ](https://hackmd.io/@YMont/python-fastapi-4)

**Python - Flask**
* 2021.11 [後端學習紀錄 Backend with Flask (1) - Website with Database](https://hackmd.io/@YMont/python-flask-1)
* 2021.11 [後端學習紀錄 Backend with Flask (2) - Website with UI](https://hackmd.io/@YMont/python-flask-2)

**--Frontend--**
**React**
* 2021.11 [Day1學前端 Frontend with React (1) - Start React](https://hackmd.io/@YMont/frontend-react-day1)
* 2021.11 [Day2學前端 Frontend with React (2) - Hello World React](https://hackmd.io/@YMont/frontend-react-day2)
* 2021.11 [Day3學前端 Frontend with React (3) - 串接API with Ajax](https://hackmd.io/@YMont/frontend-react-day3)
* 2021.11 [Day4學前端 Frontend with React (4) - show on UI](https://hackmd.io/@YMont/frontend-react-day4)

## C Learning
* 2021.08 [Swap-Function_File-Separation](https://hackmd.io/@YMont/ry2AS-A1Y)
* 2021.08 [圖解資料結構:使用C語言 Array](https://hackmd.io/@YMont/c-learning-DS-graph)

## Python Learning
* 2021.10 [Python應用Asynchronous 初探異步/同步](https://hackmd.io/@YMont/python-learning-asynchronous) 
* 2021.12 [Python 類別&裝飾器](https://hackmd.io/@YMont/python-learning-class-decorator)

## Data Structure 資料結構
* 2021.09 [Linked list-Struct 細節探討與學習(上)](https://hackmd.io/@YMont/B18SDqFXt) 
* 2021.09 [Linked list-Struct 細節探討與學習(下)](https://hackmd.io/@YMont/rJOnmacmK) 

## C make
* 2021.08 [初探Makefile](https://hackmd.io/@YMont/r1m7nsugF) 
* 2021.08 [makefile應用](https://hackmd.io/@YMont/SyopkA2lK) 

## SQL
* 2021.10 [使用Python建立SQLite DB with SQLAlchemy](https://hackmd.io/@YMont/S101piNzY) 
* 2021.10 [SQL 解題練習](https://hackmd.io/@YMont/rJQH8nEfK) 

## Protocol 通訊協定
**Modbus**
* 2021.10 [Modbus學習紀錄I](https://hackmd.io/@YMont/BJhnG-kfY)

**HTTP**
* 2021.11 [來刷一下吧 Lidemy HTTP Challenge](https://hackmd.io/@YMont/http-lidemy)

## Mountain 登山
* 2021.11 [關於登山 我是如何打怪練功的呢 (品田池有篇)](https://hackmd.io/@YMont/-mountain-池有品田)

---

## test
* 2022.01 [Connectivity Manager API WAN篇](https://hackmd.io/@YMont/CM_wan)
* 該函式裡呼叫多次setValIfExist函式
1.可給定兩個參數，若參數1不為空則回傳本身；若為空，則回傳預設的空字串(值)
2.所以，理論上操作設定WAN時，都要把每個空格填入值；推測跟UI畫面呈現方式有關吧!
* 函式create_nat_config_for_wan_apttern裡面細節
(這個函式裡面很多**NAT**實作細節，需要另開一篇撰寫)
1.大概就是開啟一個`natcfg.sh`檔案與`natcfg_func.sh`檔案
2.接著將物件得到的值(**wandevliststr**, **landev**, **lanip**, **lanmask**)代入`natcfg_func.sh`的變數位置
3.最後再將變更完的資料寫入`natcfg.sh`，搬移到系統位置，執行shell腳本
* 函式applyWanEthernetConnection裡面細節
1.==多了一個冗贅/cmlib/cmutils.python/ line.2208 似乎重複2209的事情==
2.==也沒有物件承接，但是該函式有回傳值，意義不明!==

---

**Part3**
`/connapi/wan.py line.73`
```python=
retobj = cmutils.getWanSettingsWithSubsettings(wanIndex=wanIndex)
msg = GeneralMessageModel.successMessage(obj=retobj)
```
