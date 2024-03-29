# pip 指令全記錄

- python更新 pip 套件 (可以使用Python命令参数-m選項来安裝，-m的意思是用Python解釋器來運行pip再更新，這目前[最推薦使用安裝方式](https://zhuanlan.zhihu.com/p/480918238)，因為`python -m pip`可以確保想安裝的包和當前的解釋器是同一個環境):
```python
python -m pip install --upgrade pip
python -m pip install -U pip
```
- 安裝套件： 可以將 flask 換成任何想安裝的 Python 套件
```python
pip install flask
```
- 更新套件(這方法如果還沒安裝套件會自動安裝，已經安裝的話則對該套件進行更新)：
```python
pip install -U flask
```
- 移除安裝過的套件：
```python
pip uninstall flask
```
- 安裝並且指定套件版本：
```python
pip install -v flask==1.0
```
- 查看目前安裝過的清單：
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

