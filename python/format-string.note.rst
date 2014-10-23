========================
= Python format string =
========================

str.format() 在 Python 2.6 中出現，在這之前只能使用 '%' 運算子

以下主要記錄 str.format()

-   文件

    https://docs.python.org/2/library/string.html#format-string-syntax

-   特別記錄: % 運算子，不定長度 padding

    >>> width = 10
    >>> x = 5
    >>> print "%0*d" % (width, x)
    0000000005

-   str.format() 基本使用

    >>> a = 'aa'
    >>> b = 'bb'
    >>> '{} {}'.format(a, b)
    aa bb
    >>> '{1} {0}'.format(a, b)
    bb aa
    >>> '{arg1} {arg2}'.format(arg1=a, arg2=b)
    aa bb

-   字串 padding

    -   置左/置右/置中

        >>> '{:<30}'.format('left aligned')
        'left aligned                  '
        >>> '{:>30}'.format('right aligned')
        '                 right aligned'
        >>> '{:^30}'.format('centered')
        '           centered           '
        >>> '{:*^30}'.format('centered')  # use '*' as a fill char
        '***********centered***********'

    -   不定長度 padding

        >>> '{num:{fill}{width}}'.format(num=123, fill='0', width=6)
        '000123'

-   搭配 dict

    >>> coord = {'latitude': '37.24N', 'longitude': '-115.81W'}
    >>> 'Coordinates: {latitude}, {longitude}'.format(**coord)
    'Coordinates: 37.24N, -115.81W'

-   百分比數值

    >>> points = 19.5
    >>> total = 22
    >>> 'Correct answers: {:.2%}'.format(points/total)
    'Correct answers: 88.64%'
