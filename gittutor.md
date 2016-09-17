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

+ 跳过暂存区域直接提交 `git commit -a`

+ 移除文件

    ```bash
    # 如果直接用 rm 命令删除则需要再运行 git rm 来记录此次移除的操作
    rm filename
    git rm filename
    
    # 如果已经加入暂存区，则不能直接用 git rm 删除
    git rm -f filename  # 强制删除

    # 如果只是需要从暂存区删除
    git rm --cached filename

    # 也可以使用目录或通配符 \ 是用git自己的匹配方式可以递归
    git rm log/\*.log   # 删除log目录下所有的 .log 结尾的文件

    git rm \*~  # 删除当前目录及子目录所有的~结尾的文件
    ```

+ 移动文件

    ```sh
    git mv file_from file_to
    ```

+ 查看提交历史

    ```sh
    git log     # 列出所有更新
    git log -p -2   # -p 展开每次提交内容的差异，-2 显示最近2次
    git log --stat  # 仅显示摘要的增改行数统计
    git log --pretty=oneline short full fuller
    git log --pretty=format:"%h - %an, %ar : %s"    # 可以格式化显示
    git log --graph # 简单的符号显示分支及其分化衍合情况
    ```

+ 限制输出长度

    ```sh
    # 如果要查看 Git 仓库中，2008 年 10 月期间，Junio Hamano 提交的但未合并的测试脚本（位于项目的 t/ 目录下的文件），可以用下面的查询命令：

    $ git log --pretty="%h - %s" --author=gitster --since="2008-10-01" \
   --before="2008-11-01" --no-merges -- t/

    选项 说明
    -(n)	仅显示最近的 n 条提交
    --since, --after 仅显示指定时间之后的提交。
    --until, --before 仅显示指定时间之前的提交。
    --author 仅显示指定作者相关的提交。
    --committer 仅显示指定提交者相关的提交。
    ```

+ 图形化工具查看

    `gitk`

+ 

   







