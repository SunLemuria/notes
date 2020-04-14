
```python
import os

os.remove()  # 删除文件
os.rename()  # 重命名
os.walk()    # 生成目录树下的所有文件名
os.chdir()   # 改变目录
os.mkdir()   # 创建目录
os.makedirs() # 创建多层目录
os.rmdir()   # 删除目录
os.removedirs()  # 删除多层目录
os.listdir()  # )列出指定目录的文件
os.getcwd()   # 取得当前工作目录
os.chmod()    # 改变目录权限
os.path.basename() # 去掉目录路径，返回文件名
os.path.dirname()  # 去掉文件名，返回目录路径
os.path.join()  # 将分离的各部分组合成一个路径名
os.path.split() # 返回(dirname(),basename())元组
os.path.splitext() # (返回 filename,extension)元组
os.path.getatime() # 最近访问时间
os.path.getctime() # 创建时间
os.path.getmtime() # 修改时间
os.path.getsize()  # 返回文件大小
os.path.isabs()    # 是否存在
os.path.isdir()    # 是否是目录
os.path.isfile()   # 是否是文件
```
