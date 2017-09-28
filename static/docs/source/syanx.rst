Sphinx语法
==========

图片链接
--------

.. image:: _static/images/apple.jpg


超链接
------

visit `baidu <http://www.baidu.com>`_
                                     
visit `baidu URL`_                           
                                                                
.. _baidu URL: http://www.baidu.com


源代码高亮显示
--------------

.. code-block:: c
    :linenos:
    :emphasize-lines: 3,6
              
    void foo()
    {
        int i;

        for(i=0; i<10; i++)
            printf("i: %d\n", a);
    }


简单表格:
---------
                                                                
=====  =====  ======                                            
   Inputs     Output                                            
------------  ------                                            
A      B      A or B                                            
=====  =====  ======                                            
False  False  False                                             
True   False  True                                                                               
False  True   True                                              
True   True   True                                              
=====  =====  ======                                            
                                                                
复杂表格样式: 
-------------
                                                               
+------------------------+------------+----------+----------+   
| Header row, column 1   | Header 2   | Header 3 | Header 4 |   
| (header rows optional) |            |          |          |   
+========================+============+==========+==========+   
| body row 1, column 1   | column 2   | column 3 | column 4 |   
+------------------------+------------+----------+----------+   
| body row 2             | Cells may span columns.          |   
+------------------------+------------+---------------------+   
| body row 3             | Cells may  | - Table cells       |   
+------------------------+ span rows. | - contain           |   
| body row 4             |            | - body elements.    |   
+------------------------+------------+---------------------+ 


引用
----

It is methioned by [Ref]_ that C++ is good.                     
                                                                
.. [Ref] 《zzq's talk》



脚注
----

orem ipsum [#f1]_ dolor sit amet ... [#f2]_                    
                                                                
Footnotes                                                       
                                                                
.. [#f1] Text of the first footnote.                            
.. [#f2] Text of the second footnote.   


列表
----

* item                                                          
* item                                                          
* item                                                          
                                                                
1. item1                                                        
2. item2                                                        
3. item3                                                        
                                                                
#. item4                                                        
#. item5                                                        
#. item6                                                        
                                                                
FOO                                                             
    this is very interesting.                                   
                                                                
BAR                                                             
    this is interesting, too. 


行内标记
--------

aaaa **加粗** aaaaa                                                
                                                                   
aaaa *倾斜* aaaaa                                                  
                                                                   
aaaaa ``引用`` aaaaaa  

段落
----

| aaaaaaaa                                                      
| bbbbbbbbb                                                     
| cccccccccccc 
