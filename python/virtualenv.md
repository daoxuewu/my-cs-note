# Virtualenv

- 安裝套件
```python
pip3 install virtualenv
```
- 創建並 cd 切換到專案資料夾內
```
mkdir project_name

cd project_name
```
- 執行 virtualenv venv 創建虛擬環境(venv可以替換成任何名稱)
- 完成即可在專案資料夾內看到多了 venv 的資料夾
```shell
# 使用環境預設 python 版本
virtualenv venv

# 指定 python 版本
virtualenv venv --python=pythonx.x.x.
```
- 啟動(進入)虛擬環境，venv名稱記得替換成創建時的名稱：
``` shell

# Windows 環境
venv\Scripts\activate

# 在 Linux 和 macOS 環境（請留意符號上的不同）
source venv/bin/activate
```
- 這個指令可以用 Visual Studio Code打開當前資料夾(順帶一提，keyboard shortcut `Ctrl + J` can get the terminal up and down):
```
code .
```
- 離開虛擬環境回到global環境:
```
deactivate
```
- 查看目前安裝的套件清單：
```python
pip list
```
- pip 安裝 requirements.txt 內的清單(一次安裝多個套件)：
```python
pip install -r requirements.txt 
```
- 將安裝過的套件建立成 requirements.txt 文件清單，專案若打算要傳給別人使用，這個指令可以表示我們這個專案用哪些模組：
```python
pip freeze > requirements.txt
```
- 刪除虛擬環境
```
rm -rf venv
```
> 補充:  
自己的虛擬環境不需要也一併複製給別人，因為每個人的作業系統環境都不一樣，自己的虛擬環境通常只適用在自己的電腦中，為了維持專案最大的相容性，並不需要也不適合把自己的虛擬環境提供給別人使用，在Python專案中，只要有requirements.txt敘明本專案所有使用到的模組和套件就可以了。  
>
>參考資料:[何敏煌老師的課程教材](https://104.es/2021/04/28/python-virtualenv-introduction/)

# 問題排解
- 在Windows上可能會遇到[輸入指令出現「因為這個系統上已停用指令碼執行，所以無法載入...」的問題](https://israynotarray.com/other/20200510/1067127387/)
