===================
.rst cheat sheet
===================


概要
======================


見出し
==========

reSTでは、以下の文字のいずれかを、見出しにしたい文字列の下に引くことで見出しになります。
:: 
  # * = - ^ " ' ` ~ + : < > _

これらの記号が出てきた順で見出しの大きさが決まります。
推奨は以下です。
:: 
   =====
   例h1
   =====
  
   例h2
   =====

   例h3
   -----

   例h4
   ^^^^^

=====
例h1
=====

例h2
=====

例h3
-----

例h4
^^^^^

文字の装飾
============
:: 

   **Bold Text**

**Bold Text**

:: 

   *Italic Text*

*Italic Text*

::

   "Code Text"

"Code Text"

:: 

   `` Monospaced Font `` 
   
``Monospaced Font`` 


引用文
========

:: 

   ここは普通の文章
   
      ここは引用文
      
   ここは普通の文章

ここは普通の文章

   ここは引用文

ここは普通の文章

コードブロック
===============

reSTでは、コードブロック直前の段落を「:: 」で終わらせると次の段落がコードブロックになります。

:: 
   
   ここは普通の段落:: 
   
      インデントがなくならない限りコードブロック
      改行
      
      空行を挟んだ複数行も可
   
   ここは普通の段落

ここは普通の段落:: 

   インデントが…
   改行
   
   空行を…

ここは普通の段落

コードサンプル
===============
code-blockディレクティブを使う

:: 

   .. code-block:: c
   
      # include <stdio.h>
      
      int main(void) {
         printf("Hello world");
      }

.. code-block:: c

   # include <stdio.h>
   
   int main (void) {
      printf("Hello world");
   }

リンク
========

:: 

   `Google <https://www.google.co.jp/>`_

`Google <https://www.google.co.jp/>`_

リスト
=======

:: 

   */-/+のどれか
   
   * リスト1
   * リスト2
   * リスト3
   
   ナンバリング
   
   1. リスト1
   2. リスト2
   3. リスト3
   
   自動ナンバリング
   
   #. リスト1
   #. リスト2
   #. リスト3
   
   ネスト
   
   * 親
   
      #. 子（空行を挟む）

* リスト1
* リスト2
* リスト3

1. リスト1
2. リスト2
3. リスト3

#. リスト1
#. リスト2
#. リスト3

* 親

   #. 子

水平線
===========

見出しに使える文字を4つ以上並べて前後を空行とする

:: 

   水平線
   
   ====
   
   suiheisen

水平線

====

suiheisen

画像
=======
imageディレクティブを使う

:: 

   .. image:: ../image.png
      :alt: IMAGE

表
=======

:: 

   グリッドテーブル
   
   +-----+-------+
   | 値 | 説明 |
   +=====+=======+
   | 値1 | 説明1 |
   +-----+-------+
   | 値2 | 説明2 |
   +-----+-------+
   | 値3 | 説明3 |
   +-----+-------+
   
   シンプルテーブル
   
   ==== ======
   値 説明
   ---- ------
   値1 説明1
   値2 説明2
   値3 説明3
   ==== ======

+-----+-------+
| 値 | 説明 |
+=====+=======+
| 値1 | 説明1 |
+-----+-------+
| 値2 | 説明2 |
+-----+-------+
| 値3 | 説明3 |
+-----+-------+

==== ======
値 説明
---- ------
値1 説明1
値2 説明2
値3 説明3
==== ======

数式
========

conf.pyに以下を追加した後にmathディレクティブを使う
:: 

   conf.py
   
   extensions = ['sphinx.ext.mathjax']

:: 

   .. math:: 
   
   b = a^e \mod n


参考
======

varsion
=========
