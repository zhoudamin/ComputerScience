# Linux基础(一)
## Linux 操作系统的核心是什么？
内核(Kernel)是Linux 操作系统的核心。

```text
Shell是一个命令行解释器
命令（Command）是针对计算机的指令
脚本(Script)是存储在文件中的命令的集合
终端(Termial)是命令行接口
```
## 一般的 Linux 命令的语法格式是：
Command [选项] [参数]

##  linux的特点 
             - 免费的/开源 
             - 支持多线程/多用户 
             - 安全性好 
             - 对内存和文件管理优越 
             
## 常用命令介绍 
         pwd，显示当前在哪个路径下 
   
         linux的用户管理 
         useradd 用户名，添加用户 
         【案例】useradd xiaoming
         passwd 用户名，为新用户设密码 
         【案例】passwd xiaoming，修改小明的密码 
         userdel 用户名，删除用户 
         【案例】userdel xiaoming，删除用户但保存用户主目录 
         【案例】userdel ‐ xiaoming，删除用户以及用户主目录 
         logout，当前用户推出 
         who am i，当前用户是谁 
   
         cd，改变目录 
         ls，列出文件和目录 
         ls ‐a，显示目录下的所有文件，包括隐藏文件 
         ls ‐l，显示长列表格式 
         mkdir，建立目录 
         rmdir，删除空目录 
         touch，建立空文件 
         cp，复制命令 
         【案例】cp ‐r dir1 dir2，递归复制命令（复制子目录信息） 
         mv，移动文件和改文件名 
         rm，删除文件和目录 
         rm ‐rf *，删除所有内容，包含目录和文件，r表示递归，f表示强制 
         ln，建立符号连接，类似于建立某个文件的快捷方式 
         ln ‐s 源目标 
         【案例】ln ‐s /etc/inittab inittab，inittab指向实际文件/etc/inittab inittab 
         more，显示文件内容带分页，ctrl + page up上翻，长空格下翻 
         less，显示文件内容带分页 
         grep，在文本中查询内容 
         【案例】假设存在某个文件test.java中含有hanyang关键字，此时可以使用grep名命令来查找，grep n “hanyang” test.java，n表示在第n行出现 
         |，管道命令，在linux和unix系统，把上一个命令的结果交给|后面的命令处理 
         【案例】ls ‐l /etc/ | more 
  - man [command]，帮助，类似于dos中的help 
     
   - find，搜索文件及目录。在linux中，因为文件系统是以级别式的结构来组成的，所以要在整个系统中找到特定的文件和目录并不是件容易的事。而“find”命令可以解决上述问题 
   - 在特定的目录下搜索并显示指定名称的文件和目录 
   【案例】find / -name man：意思是说从根目录开始搜索名称为man的文件或目录 
   - 搜索一段时间内被存取/变更的文件或目录 
   【案例】find /home -amin -10：十分钟内存取的文件或目录 
   【案例】find /home -atime -10：十小时内存取的文件或目录 
   【案例】find /home -cmin -10：十分钟内更改过的文件或目录 
   【案例】find /home -ctime +10：十小时前更改过的文件或目录 
   
   - 搜索指定大小的文件 
   【案例】find /home -size +10k：意思是说查找/home目录下大小为10k的文件 
   
   - 重定向命令 
   - ls -l > a.txt，列表的内容写入文件a.txt中（覆盖写） 
   - ls -al >> aa.txt，列表的内容追加到文件aa.txt的末尾 
   - 从文件中输入信息：database_program < database_data 
   - en，查看环境变量 
   
   - 压缩和解压 
   - 以zip和unzip处理.zip文件 
   - zip命令的基本使用方法 
   - zip file.zip *：zip后接压缩后的文件名，在它的后面输入要压缩的文
   件即可 
   - 压缩后，自动删除原文件 
   【案例】zip m file.zip to.txt：把to.txt文件压缩成file.zip文件，to.txt会自动删除的 
   - 将子目录一起压缩 
   【案例】zip ‐r file.zip *：将当前目录下的子目录一起压缩 
   - 忽略子目录的内容 
   【案例】zip ‐j file.zip * 
   - 将已压缩的或没有必要压缩的文件去掉 
   【案例】zip ‐n .mpg: .jpg: .gif：第一种文件中间要用“：”分开 
   - 压缩某一日之后的文件 
   【案例】zip ‐t 102002 file.zip：将当前目录下在2002年10月20日之后文件压缩 
   - 不压缩链接文件的原文件 
   【案例】zip ‐y file.zip * 
   - 压缩率问题，-1~-9，其中-9的压缩率最高 
   【案例】zip -9 file.zip * 
   - 将不需要压缩的文件排除在外 
   【案例】zip file.zip * -x file2.txt：在压缩时，将当前目录内的file2.txt文件排除在外 
   - 以unzip命令进行.zip文件的解压缩 
   - 直接解压缩文件 
   【案例】unzip file.zip 
   - 排除不需要解压缩的文件 
   【案例】unzip file.zip ‐x file2：除了file2文件外，其他的文件都解压缩 
   - 查看压缩包的内容 
   【案例】unzip ‐Z file.zip：查看file.zip压缩包的内容，也可以使用“-l” “-v”来查看压缩包的内容 
   - 以gzip和gunzip处理.gz文件 
   
   
         在linux中的每个用户必须属于一个组，不能独立于组外。在linux中每个文件有所有者、所在组、其它组的概念 。
   1）所有者：一般为文件的创建者，谁创建了该文件，就天然的成为该文件的所有者。用ls ‐ahl命令可以看到文件的所有者。也可以使用chown 用户名 文件名来修改文件的所有者。
   2）文件所在组：当某个用户创建了一个文件后，这个文件的所在组就是该用户所在的组，用ls ‐ahl命令可以看到文件的所有组，也可以使用chgrp 组名 文件名来修改文件所在的组。
   3）其它组：除开文件的所有者和所在组的用户外，系统的其它用户都是文件的其它组。
   
   
   文件权限 
         ls -l中显示的内容如下： 
         -rwxrw-r‐-1 root root 1213 Feb 2 09:39 abc 
   
   - 10个字符确定不同用户能对文件干什么 
   - 第一个字符代表文件（-）、目录（d），链接（l） 
   - 其余字符每3个一组（rwx），读（r）、写（w）、执行（x） 
   - 第一组rwx：文件所有者的权限是读、写和执行 
   - 第二组rw-：与文件所有者同一组的用户的权限是读、写但不能执行 
   - 第三组r--：不与文件所有者同组的其他用户的权限是读不能写和执行 
   也可用数字表示为：r=4，w=2，x=1 因此rwx=4+2+1=7 
   
   - 1 表示连接的文件数 
   - root 表示用户 
   - root表示用户所在的组 
   - 1213 表示文件大小（字节） 
   - Feb 2 09:39 表示最后修改日期 
   - abc 表示文件名 
   
   改变权限的命令 
   chmod 改变文件或目录的权限 
   chmod 755 abc：赋予abc权限rwxr-xr-x 
   chmod u=rwx，g=rx，o=rx abc：同上u=用户权限，g=组权限，o=不同组其他用户权限 
   chmod u-x，g+w abc：给abc去除用户执行的权限，增加组写的权限 
   chmod a+r abc：给所有用户添加读的权限 
   
   改变所有者（chown）和用户组（chgrp）命令 
   chown xiaoming abc：改变abc的所有者为xiaoming 
   chgrp root abc：改变abc所属的组为root 
   chown root ./abc：改变abc这个目录的所有者是root 
   chown ‐R root ./abc：改变abc这个目录及其下面所有的文件和目录的所有者是root 
   
   改变用户所在组 
   在添加用户时，可以指定将该用户添加到哪个组中，同样用root的管理权限可以改变某个
   用户所在的组 
   - usermod ‐g 组名 用户名 
   你可以用 - usermod ‐d 目录名 用户名，改变该用户登录的初始目录 
   
   linux分区详解 
   硬盘的分区主要分为基本分区（Primary Portion）和扩展分区（Extension Portion）两种。只是针对一个硬盘来讲，基本分区和扩展分区的数目之和不能大于4个，且基本分区可以马上被使用但不能再分区。扩展分区必须再进行分区后才能使用，也就是说它必须还要进行二次分区。那么有扩展分区再分下去的是什么呢？它就是逻辑分区（Logical Portion），而且逻辑分区没有数量上限制 
   
   对windows用户来说，有几个分区就有几个驱动器，并且每个分区都会获得一个字母标识符，然后就可以选用这个字母来指定在这个分区上的文件和目录。它们的文件结构都是独立的，非常好理解。但对这些用户初上手Redhat Linux，可就有点恼人了。因为对Redhat Linux用户来说无论有几个分区，分给哪一个目录使用，它归根结底就只有一个根目录、一个独立且唯一的文件结构。Redhat Linux中每个分区都是用来组成整个文件系统的一部分。因为它采用了一种叫“载入”的处理方法，它的整个文件系统中包含了一整套的文件和目录，并将一个分区和一个目录联系起来。这时要载入的那个分区将使它的存储空间在这个目录下获得。
   
   几个重要命令 
   挂载命令 
   mount [-parameters] [设备名称] [挂载点] 
   卸载命令 
   umount [挂载点] 
   查看磁盘使用情况 
   df [-parameters] 
   - df -h 
   - df ‐l 
   - df [目录全路径]，查看某个目录是在哪个分区 
   
   查看linux系统分区具体情况 
   fdisk ‐l 
   
   shell编程 
   其实作为命令语言互动式地解释和执行用户输入的命令只是shell功能的一个方面。shell还可以用来进行程序设计。它提供了定义变量和参数的手段以及丰富的程序控制结构。使用shell编程类似于DOS中批处理文件，称为shell script，又叫shell程序或shell命令文件。
   
   shell脚本文件： 
   - 是一个文本文件 
   - 命令的集合 
   - 有执行的权限 
   - 执行方式（./文件名） 
   
   用export可以临时加入一个系统路径，如export PATH=$PATH:$HOME/bin:/root/test/t1，输出环境PATH，引用原来的值$PATH，$HOME表示工作主目录，:是路径分隔符 
   
   shell通配符 
   - *代表多个字母或数字 
   - ?代表一个字母或数字 
   【案例】ls a* ls a? ls f080[1-6].tif 
   
   
   - 转义字符\ 
   【案例】ls /mnt/win1/My\Documents 
   
   - 单引号：不处理任何变量和命令 
   【案例】echo ‘Welcome $NAME, the date is date ’ 
   
   - 双引号：处理变量但不处理命令 
   【案例】echo “Welcome $NAME, the date is date “ 
   
   - 反引号：把引号中的每个单词作为一个命令，如果是变量则先求值然后作为一个命令处理 
   【案例】echo “Welcome $NAME, the date is `date` “ 
   
   
   查阅历史记录 
   - history，查看使用过的命令的历史记录 
   - history 5，此项说明会显示最近使用的5个命令 
   - !5，此项说明执行历史编号为5的命令 
   - !ls，此项说明执行最后一次以“ls”开头的命令
## 
## 
## 
## 
## 
## 