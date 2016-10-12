##本书gitbook使用

本书有两个分支： master(书籍源码),gh-pages（书籍生成的静态网页）

推荐安装：首先安装nvm，再使用nvm安装node,再安装gitbook

gitbook在本地预览书籍

        gitbook serve

gitbook编译(编译到_book文件夹下了)

        gitbook build
        

将gh-pages分支clone到gh-pages文件夹下

        git clone -b gh-pages https://github.com/freehuoshan/springsecurity-reference-cn.git gh-pages
        
        
每次修改书籍后，编译后将_book下所有文件拷贝到gh-pages下，push

在master的.gitignore文件中忽略_book和gh-pages文件夹

## SpringSecurity 指北手册中文翻译


> 希望由更多人和我一起翻译

