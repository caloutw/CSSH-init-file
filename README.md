# CSSH-init-file
CSSH初始化技術文檔支持


# 初次上手
初次上手必須使用 PC 端作為媒介<br>
您可以使用以下工具
- Windows
  - CMD
- MacOS, Linux
  - Terminal
- iPad
  - [](https://apps.apple.com/tw/app/termius-modern-ssh-client/id549039908)

- 全平台
  - [Visual Studio Code](https://code.visualstudio.com/) ([Cursor](https://cursor.com/zh-Hant), [VSCodeium](https://vscodium.com/) 等)

# 如何連線(CMD Terminal)
如果你使用的是 CMD Terminal，指令如下
```shell
ssh <yourname>@ssh.calou.cc -p <port>
```
如果詢問金鑰，則輸入Yes後，輸入密碼

# 如何連線(VSCode)
左下角的 SSH箭頭 按鈕<br>
> 如果你是第一次，則要安裝 "Remote-SSH"

然後選擇 "Connect to Host..."<br>
他會要你輸入東西，請輸入<br>
```shell
ssh <yourname>@ssh.calou.cc -p <port>
```
> 如果是第一次，請先輸入 Yes 後等他連線

然後輸入密碼

# 如何連線(Termius)
創建一個新的SSH實例即可，遵循上面需要的輸入

# 概念
首先，這是專業區域了，基本上比 code-server還專業<br>
我們給您配置了兩個對外的port，分別是3000 3100<br>
對應的入口是 web.\<yourname\>.calou.cc(3000) & dev.\<yourname\>.calou.cc(3100)<br>

# 如何使用
請先啟動 SSH 的 Terminal(前提你要是VSCode用戶，如果你是用CMD Terminal連線的，那這步就忽略)
輸入
```shell
curl -O https://calou.cc/linux/vscInit.sh && chmod 777 vscInit.sh
```
然後執行
```shell
./vscInit.sh
```
基本上你要安裝得有(必須): 5<br>
如果你需要code-server，請安裝 1<br>
剩下的自己看著辦

# Tmux
這是每個 SSH 開發者必學，這個是替代code-server可以背景執行的套件<br>
```sh
tmux new -t Siromiku  #新視窗，名稱為Siromiku
```
```sh
tmux ls #查看所有視窗
```
```sh
tmux kill-session -t Siromiku  #移除名稱為Siromiku的視窗
```
```sh
tmux a -t Siromiku #進入名稱為Siromiku的視窗
```
```sh
tmux kill-session -a #全部移除
```
如果要離開該視窗，Ctrl+B 再按 D

# 開啟code-server

### ~~注意！此方法一定要使用 CMD & Terminal & Termius，VSC一定報錯~~

請先開一個tmux視窗，名稱隨便叫，在裡面執行
```shell
code-server
```
然後前往<br>
dev.\<yourname\>.calou.cc<br>

# 最後
記住，任何code-server的東西都要創建新的tmux實例，一個項目一個，否則你會打結的。
