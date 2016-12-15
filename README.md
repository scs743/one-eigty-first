Python 运行环境使用的是 Python 2.7.9。

仅支持运行纯 Python 的应用，不能动态加载 C 扩展，即.so，.dll 等格式的模块不能使用
进程，线程操作受限
本地文件系统只读。应用可以读取本应用目录，Python 标准库下的内容，如需读写临时文件建议使用 StringIO 或者 cStringIO 来替代。
Python 默认的模块搜索路径为：当前目录 > 系统目录。添加模块搜索目录的方法为：

import sys
sys.path.insert(0, your_custom_module_path)
注意：Python 当前目录下的子目录只有包含__init__.py 才会被 Python 认为是一个 package，才可以直接 import。

用户可以上传和使用 .pyc 文件，注意 .pyc 文件必须是 python2.7.9 生成的，否则无效。

Python 运行环境设置了一些自定义的环境变量，这些环境变量可以通过 os.environ 这个 dict 获取。

APP_NAME：应用名。
APP_VERSION: 当前应用使用的版本号。
SERVER_SOFTWARE: 当前 server 的版本（目前为 direwolf/0.1）。 可以使用这个环境变量来区分本地开发环境还是在线环境，本地开发环境未设置这个值。
