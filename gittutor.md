## git 学习笔记

**所有的笔记内容来自：http://www.open-open.com/lib/view/open1328069609436.html**

+ 全局配置

    ```bash   
    # 配置用户名和邮箱(全局的),如果需要配置某个项目特定用户去掉 --global即可
    git config --global user.name "aoenian"
    git config --global user.email aoenian@zoho.com.cn

    # 文本编辑器设置
    git config --global core.editor vim

    # 差异分析工具
    git config --global merge.tool vimdiff

    # 查看配置信息
    git config --list
    ```

+ 初始化 `git init`

+ 克隆仓库 `git clone url name.clone`

+ 文件状态 `git status`

+ 跟踪或暂存文件 `git add file` `git add -A`

+ 运行了 `git add` 之后又修改的文件，需要再次暂存即再次运行 `add`

+ 忽略某些文件 .gitignore

    ```
    # 此为注释 – 将被 Git 忽略
    # [abc] 匹配任何一个方括号中的字符
    # ? 只匹配一个任意字符
    # [0-9] 匹配所有0-9的数字
    *.a       # 忽略所有 .a 结尾的文件
    !lib.a    # 但 lib.a 除外
    /TODO     # 仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO
    build/    # 忽略 build/ 目录下的所有文件
    doc/*.txt # 会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
    ```

+ 查看尚未暂存的文件更新了哪些部分 `git diff`
    
    如果需要比较暂存的文件和上次快照的文件的差异，请使用 `git diff --cache`
或者 `git diff --staged`

+ 提交更新 `git commit` `git commit -m "message"`







