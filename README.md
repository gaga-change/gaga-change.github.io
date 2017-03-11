## 博客说明

> 通过`Jekyll Writer` 自动创建

## 本地运行环境

ruby

### 下载jekyll

	gem install jekyll

### 运行

	jekyll serve

### 文件标题含中文时需要更改配置文件

找到安装目录 \Ruby22-x64\lib\ruby\2.2.0\webrick\httpservlet下的filehandler.rb文件
更改前先备份

找到以下两次进行更改（+ 的一行为添加的部分）
1.


    path = req.path_info.dup.force_encoding(Encoding.find("filesystem"))
    + path.force_encoding("UTF-8") # 加入编码
    if trailing_pathsep?(req.path_info)
        
2.


    break if base == "/"
    + base.force_encoding("UTF-8") #加入編碼
    break unless File.directory?(File.expand_path(res.filename + base))
   	