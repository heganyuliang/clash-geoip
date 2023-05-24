# 一、 说明
1. 根据 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制，**有且仅有如下分类**：
```
- GEOIP,cn, 国内 IP
- GEOIP,private, 私有网络
- GEOIP,telegram, Telegram IP
```
2. 每天早上 3 点（北京时间）自动构建
3. `GEOIP:cn` 源采用 [blackmatrix7/ios_rule_script/ChinaMax](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax)（ChinaMax_IP.txt）
4. `GEOIP:private` 源采用 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（IP 部分）
# 二、 下载
## 1. geoip.dat
① GitHub 源：https://github.com/heganyuliang/clash-geoip/releases/download/latest/geoip.dat  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/heganyuliang/clash-geoip@release/geoip.dat
## 2. Country.mmdb
① GitHub 源：https://github.com/heganyuliang/clash-geoip/releases/download/latest/Country.mmdb  
② jsDelivr 源：https://cdn.jsdelivr.net/gh/heganyuliang/clash-geoip@release/Country.mmdb
# 三、 导入
## 1. 导入 ShellClash
连接 SSH 后执行如下命令：
```
curl -o $clashdir/GeoIP.dat -L https://cdn.jsdelivr.net/gh/heganyuliang/clash-geoip@release/geoip.dat
curl -o $clashdir/Country.mmdb -L https://cdn.jsdelivr.net/gh/heganyuliang/clash-geoip@release/Country.mmdb
```
## 2. 导入 Clash Verge（Windows 端）
首次使用可进入“配置”，新建”Merge“类型的配置，保存后进入文件夹 *%USERPROFILE%\.config\clash-verge\profiles*，可以看到这里新增了一个.yaml 文件，复制其文件名并替换下面命令中的{文件名}  
编辑文本文档，粘贴如下内容：
```
curl -o %USERPROFILE%\.config\clash-verge\geoip.dat -L https://cdn.jsdelivr.net/gh/heganyuliang/clash-geoip@release/geoip.dat
curl -o %USERPROFILE%\.config\clash-verge\Country.mmdb -L https://cdn.jsdelivr.net/gh/heganyuliang/clash-geoip@release/Country.mmdb
copy /y "%USERPROFILE%\.config\clash-verge\geoip.dat" "%PROGRAMFILES%\Clash Verge\resources"
copy /y "%USERPROFILE%\.config\clash-verge\Country.mmdb" "%PROGRAMFILES%\Clash Verge\resources"
```
另存为.bat 文件，右击该文件，选择以管理员身份运行
