# 打包python成exe檔

### 快速開始
一般打包輸入下列指令即可:

```python
Pyinstaller -F setup.py 打包exe

Pyinstaller -F -w setup.py 不带控制台的打包

Pyinstaller -F -i xx.ico setup.py 打包指定exe圖標打包
```

如果不想自己輸入程式碼可以用工具 [auto-py-to-exe](https://github.com/brentvollebregt/auto-py-to-exe)

```python 
# 下載 
pip install auto-py-to-exe

# 啟動
auto-py-to-exe
```

### 打包過程中需要注意的點
- 在程式碼裡面盡量不要用import，能用from……import……就盡量用這個，因為如果是import的話，在打包的時候，會將整個引用的包都打包到exe裡面，造成沒有意義的增加了打包完程式的大小!
- 程式的路徑最好全部都是英文，否則可能會出現莫名其妙的問題
- 安裝pyinstaller之前記得要把pip升級成最新版的pip再進行安裝，避免出現莫名其妙的問題。


### 參考網址
- [使用auto-py-to-exe完美打包python程序](https://zhuanlan.zhihu.com/p/130328237)
- [Python 打包成 exe 終極方案](https://www.readfog.com/a/1636267007799300096)
- [别再问我怎么Python打包成exe了！](https://mp.weixin.qq.com/s/zilDeFunWLG0mBS_x0vNnA)
- [Python 打包成 exe，太大了該怎麼解決？](https://www.zhihu.com/question/281858271/answer/613147412)

### 問題排解
- [Issues When Using auto-py-to-exe](https://nitratine.net/blog/post/issues-when-using-auto-py-to-exe/?utm_source=auto_py_to_exe&utm_medium=application_link&utm_campaign=auto_py_to_exe_help&utm_content=top)  
- [Bundling data files with PyInstaller (--onefile)](https://stackoverflow.com/questions/7674790/bundling-data-files-with-pyinstaller-onefile/13790741#13790741)

```python
def resource_path(relative_path):
    """Get absolute path to resource, works for dev and for PyInstaller (獲取程序中所需文件資源的絕對路徑)"""
    try:
        # PyInstaller creates a temp folder and stores path in _MEIPASS (PyInstaller創建臨時文件夾，將路徑儲存於_MEIPASS)
        base_path = sys._MEIPASS
    except Exception:
        base_path = os.path.abspath(".")

    return os.path.join(base_path, relative_path)
```
