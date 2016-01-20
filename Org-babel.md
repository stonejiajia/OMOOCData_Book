# 参考资料

[Python Source Code Blocks in Org Mode.](http://orgmode.org/worg/org-contrib/babel/languages/ob-doc-python.html)  

# Org-babel 介绍

在Org-mode上进行文学编程，类似Ipython-notebook，但Org-babel最大的特点在于什么语言都支持。
只需要在你的.emacs里加入你需要的语言。

    (org-babel-do-load-languages
          'org-babel-load-languages
          '((emacs-lisp . t)
            (ruby . t)
            (ditaa . t)
            (python . t)
            (sh . t)
            (latex . t)
            (plantuml . t)
            (R . t)))

# Org-babel的基本操作

输入<s Tab会生成模板供写代码使用，然后再输入你想要编写的语言

    #+BEGIN_SRC Python
    print 'Hello,world!'
    a = 1
    b = 1
    #+END_SRC

在第一行的最后加上 -n 和 -r会出现这样的效果

    #+BEGIN_SRC python -n -r
    print 'Hello,world'
    a = 1
    b = 1
    #+END_SRC

    1  print 'Hello,world'
    2  a = 1
    3  b = 1

# 在Org-babel中对Python进行编程

## Language-Specific Header Arguments

-   :results {output, value}:  Value mode是默认的，在Value-mode下还有这几个类型
    -   raw: Value 被直接插入
    -   pp:  Value 先由Python pprint.pformat(%s)，然后再插入
    -   file：Value 输入成文件名，然后在被输出，通常用于图形输出
-   ：preamble：
-   ：return: Value返回（只有当返回的类型是Value）

## Common Header Arguments

-   ：session [name]: 默认是没有session
-   ：var data=data-table: Variables 能够从Org-mode Tables 转变成Python中的列表
-   ：exports {code, results, both, none}:标准的Bable选项，选择什么类型作为输出

## Sessions

-   Session mode 用来定义函数，设置变量，和在source blocks上分享代码
-   Session mode 和 非Session mode下的有些许不一样的地方，non-session mode会被函数定义给

绊住，需要返回一个Value，所以你必须用return申明一下

### Session mode:


    def foo(x):
      if x>0:
        return x+1
      else:
        return x-1
    
    foo(1)

### Non-session mode:


    def foo(x):
      if x>0:
        return x+1
    
      else:
        return x-1
    
    return foo(5)

## 如何在Org-mode上用Python输出图形

Python的Matplotlib库可以画出图形，而Org-mode能够显示图片
所以Org-babel的另外一个优势是能够\*\*运行Python代码输出图片\*\*

    #+begin_src python :session :results file
    import matplotlib
    matplotlib.use('Agg')
    import matplotlib.pyplot as plt
    fig=plt.figure(figsize=(3,2))
    plt.plot([1,3,2])
    fig.tight_layout()
    plt.savefig('images/myfig.pdf')
    'images/myfig.pdf' # return this to org-mode
    #+end_src

    #+RESULTS:
    [[file:images/myfig.pdf]]

## 输出类型

-   value: Value
-   output: Output 的输出结果，会由Python Print出来
