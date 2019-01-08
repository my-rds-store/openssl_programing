.. openssl_programing documentation master file, created by
   sphinx-quickstart on Wed Dec 26 15:05:28 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

openssl 编程
==============================================

* `OpenSSL 1.1.1 DOCS <https://www.openssl.org/docs/man1.1.1/>`_ 
* `OPenSSL 1.0.1c Documentation  <https://docs.huihoo.com/doxygen/openssl/1.0.1c/index.html>`_

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   03.rst
   04.rst
   05.rst
   06.rst
   07.rst
   11.rst
   20.rst
   21.rst
   faq.rst

   
* `国家密码管理局关于发布 《SM2椭圆曲线公钥密码算法》公告 <http://www.oscca.gov.cn/sca/xxgk/2010-12/17/content_1002386.shtml>`_

::

    SM2椭圆曲线公钥密码算法推荐曲线参数

    推荐使用素数域256位椭圆曲线。
    椭圆曲线方程：y
    2 = x
    3 + ax + b。
    曲线参数：
    p=FFFFFFFE FFFFFFFF FFFFFFFF FFFFFFFF FFFFFFFF 00000000 FFFFFFFF FFFFFFFF
    a=FFFFFFFE FFFFFFFF FFFFFFFF FFFFFFFF FFFFFFFF 00000000 FFFFFFFF FFFFFFFC
    b=28E9FA9E 9D9F5E34 4D5A9E4B CF6509A7 F39789F5 15AB8F92 DDBCBD41 4D940E93
    n=FFFFFFFE FFFFFFFF FFFFFFFF FFFFFFFF 7203DF6B 21C6052B 53BBF409 39D54123
    Gx=32C4AE2C 1F198119 5F990446 6A39C994 8FE30BBF F2660BE1 715A4589 334C74C7
    Gy=BC3736A2 F4F6779C 59BDCEE3 6B692153 D0A9877C C62A4740 02DF32E5 2139F0A0


* `国密SM2算法 <http://8btc.com/thread-217435-1-1.html>`_
* `国家标准全文公开系统 - sm2 <http://www.gb688.cn/bzgk/gb/std_list?p.p1=0&p.p90=circulation_date&p.p91=desc&p.p2=32918>`_
* `密码行业标准化技术委员会 <http://www.gmbz.org.cn/main/bzlb.html>`_

::

    《GBT 32918.1-2016 SM2椭圆曲线公钥密码算法 第1部分：总则》，第四章节提到椭圆曲线上点的压缩与解压缩。
       这样SM2的公钥将可以占用更少的字节数。
    《GMT 0009-2012 SM2密码算法使用规范》对SM2PublicKey做出规定，
       使用非压缩方式，Bit String类型，内容是04||X||Y。

    $ gmssl genpkey -algorithm EC -pkeyopt ec_paramgen_curve:sm2p256v1 -out private.pem
    $ gmssl pkey -pubout -in private.pem -out public.pem

其他
-------



* `OpenSSL 1.1.1 新特性: 全面支持国密SM2/SM3/SM4加密算法 <https://www.jianshu.com/p/a1c3ee349345>`_



待整理 
---------

* `OpenSSL 中文手册 之 OpenSSL 简介 <https://blog.csdn.net/xiyuan1999/article/month/2011/05/2>`_

* SM2
    * `小王的尴尬日常（一）--使用RSA公钥证书解密 <https://blog.csdn.net/I_can_do_1098/article/details/54583148>`_
    * `小王的尴尬日常（二）---Openssl 实现国密算法(基础介绍和产生秘钥对) <https://blog.csdn.net/I_can_do_1098/article/details/59117569>`_
    * `小王的尴尬日常（三）--Openssl 实现国密算法 (加密和解密) <https://blog.csdn.net/I_can_do_1098/article/details/61919869>`_
    * `小王的尴尬日常（四）--openssl 实现国密算法 (签名和验签) <https://blog.csdn.net/I_can_do_1098/article/details/62045985>`_
    * `椭圆曲线加密系统之OpenSSL <http://www.jiamisoft.com/blog/16394-opensslqianrushieccquxianjiam.html>`_

-----

    * `椭圆曲线密码学在OpenSSL中的实现 <https://solobearchn.github.io/2018/03/18/ECC/>`_

    * `通过openssl生成sm2的公私钥的方法 <https://blog.csdn.net/dong_beijing/article/details/81365060>`_
    * `在openssl中对SM2的公私钥进行加解密的验证 <https://blog.csdn.net/dong_beijing/article/details/81390710>`_

* BIO
    * `OpenSSL中文手册之BIO库详解 <https://blog.csdn.net/liao20081228/article/details/77193729>`_
    * `Openssl之BIO系列 <https://blog.csdn.net/zhangzq86/article/details/50786513>`_
    * `openssl之BIO系列(01-25)(带目录) <https://wenku.baidu.com/view/2f9df64d2e3f5727a5e962a8.html>`_


* BIGNUM
    * `Openssl中的BIGNUM运算函数(整理) <https://blog.csdn.net/jnxxhzz/article/details/81235981>`_


* EVP
    * `openssl之EVP系列 <http://www.newsmth.net/bbs0an.php?path=%2Fgroups%2Fcomp.faq%2FSecurity%2Fsecuritydocs%2Fopenssl%2Fopenssl_evp>`_

* PEM
    * `openssl之PEM系列 <http://www.newsmth.net/bbs0an.php?path=%2Fgroups%2Fcomp.faq%2FSecurity%2Fsecuritydocs%2Fopenssl%2Fopenssl_pem>`_


.. code:: sh

    # sm2 test
    cd /home/vagrant/encode_src/src/openssl-1.1.1/test/
    bash sm2_build.sh

    # gmssl
    export LD_LIBRARY_PATH='/home/vagrant/usr/lib'
    export PKG_CONFIG_PATH='/home/vagrant/usr/lib/pkgconfig'
    cd /mnt/workspace/GmSSL/test
    ./sm2test

------

* `中国银联PIN算法标准 <https://max.book118.com/html/2017/0406/99012119.shtm>`_
* `银联卡中关于CVN/CVN2/ICVN的区别 <https://blog.csdn.net/chong89125/article/details/72918140/>`_

::

    openssl site:http://www.newsmth.net

------

* `Download Win32 OpenSSL <https://slproweb.com/products/Win32OpenSSL.html>`_

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
