02 python para o dia a dia
---------------------------

.. raw:: pdf

    PageBreak longPage

Baterias incluidas
----------------------

Random
---------

.. code-block:: python

    import random

    random.random()
    random.randint(start,end)   # inclui
    random.randrange(start,end) # não inclui
    random.shuffle(lista)       # no lugar
    random.choice(lista) # escolhe um elemento

randint, randrange
------------------

.. code-block:: python

    from random import randint, randrange

    valor_int = -1
    valor_range = -1
    for i in range(1000):
        valor_int = max(valor_int, randint(0,100))
        valor_range = max(valor_range, randrange(0,100))
    print valor_int, valor_range


urllib e urlib2
----------------

GETS

.. code-block:: python

    import urllib2

    url = "http://google.com/"
    resp = urllib2.urlopen(url)
    resp.read()

urllib e urlib2
----------------

POSTS

.. code-block:: python

    import urllib

    data = urllib.urlencode({"dia":12}) 
    resp = urllib2.urlopen(url, data)

pickle
------

Serialização e desserialização

.. code-block:: python

    import pickle

    foobar = [(1,2), "queijoquente"]
    pickle.dump(foobar, open("foobar.pickle", "w"))

    lerolero = pickle.load(open("foobar.pickle", "r"))
    print lerolero

sys e os
----------

Vale um estudo em separado

Dentre os usos, o que eu gosto é manipulações de caminhos

.. code-block:: python

    import sys, os
    caminho = os.path.abspath(os.path.split(__file__)[0])
    scripts = os.path.join(caminho,'scripts') 
    sys.path.append(scripts)

glob
----

listagem simples de arquivos

.. code-block:: python

    from glob import glob
    for filename in glob( '*.rst' ):
        print filename

.. " **


Facil de conseguir mais baterias
--------------------------------

Repositorio do Pypi

Python Package Index

.. code-block:: bash
    
    http://pypi.python.org/pypi

easy_install e pip
------------------

Fazem parte do pacote setup_tools

.. code-block:: bash

    $ sudo easy_install pip


ipython
----------------

.. code-block:: bash

    $ sudo pip install ipython
    $ ipython 

ipython que salva vida
----------------------

.. code-block:: python

    foo?
    foo??

    %edit
    %edit -p
    %logstart

BeautifulSoup
-------------

Incrivel scraping

Lida com html e xml mesmo quebrado

.. code-block:: bash

    sudo pip install BeautifulSoup

Pegando os links
------------------

.. code-block:: python

    import urllib2
    from BeautifulSoup import BeautifulSoup

    c = urllib2.urlopen("http://canaisglobosat.globo.com/")
    soup = BeautifulSoup(c.read())
    links = soup("a")
    for link in links:
        print link['href']


Analise bayesiana
-----------------

.. code-block:: bash

    sudo pip install reverend

Pegando os links
------------------

.. code-block:: python

    from reverend.thomas import Bayes

    bayes = Bayes()
    bayes.train("spam", "ganhe dinheiros")
    bayes.train("spam", "compre viagra")
    bayes.train("ham", "vamos a festa?")

    bayes.guess("a festa vai ser boa?")
    [('ham', 0.99990000000000001)]
    

Salvando a base treinada
------------------------

.. code-block:: python

    bayes.save(filename)
    bayes.load(filename)



feedparser
----------

.. code-block:: bash

    sudo pip install feedparser

usando
------

.. code-block:: python
    
    url = "http://multishow.globo.com/RSS/feeds/multishow.xml" 

.. code-block:: python
    
    import feedparser
    import urllib2

    feed = urllib2.urlopen(url).read()
    f = feedparser.parse(feed)
    for entry in f['entries']:
        print entry['title']

