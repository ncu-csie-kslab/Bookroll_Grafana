# Grafana 安裝教學
**一. 預先安裝
請確認Bookroll、Mysql是否已經安裝**

系統名稱       | 系統類型           | 
--------------|:-----------------:|
Moodle        | 帳號單一登入系統   |  
Bookroll      | 電子書平台        |  
MySQL         | Bookroll資料庫    | 


**二. 系統流程圖**
![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/flow_chart.png)


**三. 安裝前需求**
* 系統為Linux / Windows皆可

* Python3
  * Ubuntu已有內建
  * Windows可下載  
  
    https://www.python.org/downloads/
  * 需求套件 : lti, oauthlib, flask
   ```python
   pip install lti
   pip install oauthlib
   pip install flask
   ```
* MySQL   
  * 安裝Bookroll時即安裝
  
* Grafana
  * 可選擇Linux, Windows, Mac, Docker等安裝方式與系統
  * 請參考官方文件  
  
    https://grafana.com/grafana/download?platform=linux
    

**四. Grafana配置**
* Step1. 啟動Grafana
  * 請參考官方文件  
  
    https://grafana.com/docs/grafana/latest/installation/debian/
  * Linux為例
   ```python
   sudo service grafana-server start
   ```
* Step2.用vim或其他編輯器開啟訪客模式(auth.anoymous)
  * These system settings are defined in or custom.ini
    以Linux為例，路徑為 /etc/grafana/grafana.ini
    ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/auth.anony.png)
    
* Step3.匯入Panel面板
  * Analysis tool (Dashboard) 
  
    請下載或Clone
    
    https://github.com/CH-KANG/Grafana/blob/master/Analysis%20tool%20(Dashboard)-1583397153634.json
