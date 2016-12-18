    ## str是文本序列
    ### bytes是字节序列
        * 文本是有编码的 (utf-8, gbk, GB18030等)
        * 字节没有编码这种说法
        * 文本的编码指的是字符如何使用字节来表示

    ### Python3字符串默认使用utf-8编码
    ```py
    In [73]: s = '马哥教育'

    In [77]: s.encode() 
    In [73]: s = '马哥教育' #把字符串编码为bytes
    Out[77]: b'\xe9\xa9\xac\xe5\x93\xa5\xe6\x95\x99\xe8\x82\xb2'

    In [78]: '马'.encode()
    Out[78]: b'\xe9\xa9\xac'



    In [83]: bin(0xe9)
    Out[83]: '0b11101001'


    In [84]: b = s.encode()

    In [85]: b
    Out[85]: b'\xe9\xa9\xac\xe5\x93\xa5\xe6\x95\x99\xe8\x82\xb2'

    In [86]: b.decode() # bytes.decode() 把bytes转化为str
    Out[86]: '马哥教育'

    ```
    ##  bytes
    * 除了encode外， str操作，都有对应bytes的版本， 但是传入参数也必须是bytes
    ```py
    In [87]:  b'abc'.find('b') # 参数必须也是bytes
    ---------------------------------------------------------------------------
    TypeError                                 Traceback (most recent call last)
    <ipython-input-87-90305170cb68> in <module>()
    ----> 1 b'abc'.find('b') # 参数必须也是bytes

    TypeError: a bytes-like object is required, not 'str'


    In [88]: b'abc'.find(b'b')
    Out[88]: 1

    In [90]: '马哥教育'.encode().find(b'\xa9')  # bytes的操作是按字节来的
    Out[90]: 1

    In [91]: '马哥教育'.encode()
    Out[91]: b'\xe9\xa9\xac\xe5\x93\xa5\xe6\x95\x99\xe8\x82\xb2'

    In [92]: len('马哥教育'.encode())
    Out[92]: 12

    n [94]: b.decode()  # 转化为str
    Out[94]: '马哥教育'

    In [95]: b.hex() # 转化为16进制
    Out[95]: 'e9a9ace593a5e69599e882b2'





