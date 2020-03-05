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
  * 以Linux為例
   ```python
   sudo service grafana-server start
   ```
  * 以Windows為例   
   ```python
   cd '\Program Files\GrafanaLabs\grafana\bin'
   grafana-server.exe
   ```  
* Step2.用vim或其他編輯器開啟訪客模式(auth.anoymous)
  * These system settings are defined in or custom.ini
  
    以Linux為例，路徑為 /etc/grafana/grafana.ini
    
    開啟後需要restart
   ```python
   sudo service grafana-server restart
   ```    
    ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/auth.anony.png)
    
* Step3.連接資料庫
  * 點選 Configuration    
  
  ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/Configuration.PNG)
  * 點選 Add data source
  
  ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/Add%20data%20source.PNG)
  * 點選 SQL - MySQL
  
  ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/SQL.PNG)
  
  * 填入Bookroll的MySQL ip 與 port
  
* Step4.匯入Panel面板
  * 先下載以下兩個Dashboard的模板(json檔案)
  * Analysis tool (Dashboard) 
  
    請下載或Clone
    
    https://github.com/CH-KANG/Grafana/blob/master/Analysis%20tool%20(Dashboard)-1583397153634.json
    
  * Weekly report (Dashboard) 
  
    請下載或Clone
    
    https://github.com/CH-KANG/Grafana/blob/master/Weekly%20Report-1583397606381.json

  * 點選 + → Create → import
  
  ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/import.png)
  * 分別匯入上述兩個模板
  
  ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/importjson.PNG)
  
  * 匯入完成後開啟，選擇share dashborad，並記錄下此串網址
  
  ![image](https://github.com/CH-KANG/Grafana/blob/master/Pic/link.PNG)
