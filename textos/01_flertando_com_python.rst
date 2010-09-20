01 flertando com python
-----------------------

.. raw:: pdf

    PageBreak simplePage



O prompt interativo esse ilustre desconhecido
---------------------------------------------


.. raw:: pdf

    PageBreak longPage



Chamando
---------

.. code-block:: bash

    $ python


Temos
--------------------------

.. code-block:: bash

    $ python
    Python 2.6.5 (r265:79063) 
    [GCC 4.4.3] on linux2
    Type "help", "copyright", "credits" 
    or "license" for more information.
    >>> 

 

Seu melhor amigo
--------------------------------------

.. code-block:: python

    >>> a = 5
    >>> print a
    5
    >>> b = 4
    >>> print a + b
    9


Hello world
------------

.. code-block:: python

    >>> from datetime import datetime
    >>> from time import sleep
    >>> while True: #rodar para sempre
    ...     hora = datetime.now()
    ...     print hora.strftime("%H:%M:%S")
    ...     sleep(1) #aguardar um segundo
    ... 
    
Por partes
-----------
**True** e **False** com a primeira letra em Maiuscula

.. code-block:: python

    >>> while True: #rodar para sempre
                  ^ marca o inicio do bloco
    ...     hora = datetime.now()
    ...     print hora.strftime("%H:%M:%S")
    ...     sleep(1) #aguardar um segundo
        ^^^^ a identacao tem que ser constante

padrão são 4 espaços, mas voce tem liberdade de escolher desde que seja consistente  

Blocos
----------------------

**if** / **elif** |ruby| / **else**

**for** / **else**

**while** / **else**

**try** / **except** / **finally**

**class** / **def**


Sequências
----------

Principais classes

* string e unicode

* listas e tuplas


Implica
-------

.. code-block:: python

    len(s)   # length
    min(s)   # ou max(s)
    s[i]     # iesimo item de s (base 0)
    s[i:j]   # slice do iesimo a jesimo item
    s[i:j:k] # mesma coisa com passo k
    s + t    # concaternação
    s * i    # ou i * s;  i copias de s
    x in s   # se s tem o elemento x
    x not in s # ou nao tem 


Strings
-------

* Imutaveis |java|

* suportam operações de sequência

* demarcadas com ' ou " |java| |ruby|

* multilinhas com ''' ou """ 


Strings como sequências
------------------------

.. code-block:: python

    a = "abcdef"
    len(a)   # 6 
    min(a)   # 'a'
    a[2]     # 'c'
    a[2:5]   # 'cde'
    a[2:5:2] # 'ce'
    a + "zx" # 'abcdefzx'
    a * 2    # 'abcdefabcdef'
    "b" in a     # True
    "b" not in a # False


Strings como strings
--------------------

.. code-block:: python

    a = '  abcd \n '
    a.upper() # '  ABCD \n '
    a.strip() # 'abcd'
    a.islower() # True
    # isalnum/isalpha/isdigit
    # islower/isspace/istitle/isupper  
    a.startswith("  ") # True
    # endswith
    a.find("abc") # 2
    a.split("b") # ['  a', 'cd \n ']

Magia com Slices
-----------------------------

.. code-block:: python


    a = "ola python"
    a[0]    # 'o'
    a[1]    # 'l'
    a[-1]   # 'n'
    a[-2]   # 'o'
    a[:3]   # 'ola'
    a[4:]   # 'python'
    a[:]    # 'ola python'
    a[::-1] # 'nohtyp alo'


.. |ruby| image:: ruby.png
   :width: 48px

.. |java| image:: java.png
   :width: 48px
