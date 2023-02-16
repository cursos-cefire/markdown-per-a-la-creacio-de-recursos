
# Web estàtica amb mkdocs

En aquest apartat ens centrarem a construir una pàgina web estàtica utilitzant **mkdocs**. De nou, l'aspecte de la web vindrà determinat per plantilles, encara que en aquest cas els anomenarem temes. Continuem, per tant, amb la idea principal del curs, centrar-nos en el contingut i no tant en l'aspecte, que simplement el configurarem una vegada.

Una vegada construït el nostre lloc, aprendrem a allotjar-lo a Aules i en un apartat posterior l'allotjarem en un repositori de github, per tal que estiga disponible de forma pública a través d'internet.

Abans de començar amb el desenvolupament de l'apartat, explicarem breument què és mkdocs.

## Què és [mkdocs](https://www.mkdocs.org/)?

!!!note "mkdocs"
    Mkdocs és un generador de llocs web estàtics, pren com a entrada text escrit en markdown i utilitza dissenys predefinits per crear un lloc web estàtic. Podeu modificar l'aspecte del lloc, els enllaços, les dades que es mostren a la pàgina i moltes coses més.

## Instal·lació d'mkdocs

!!!important "VSCode"
    Per a realitzar estos passos, recomanem utilitzar VSCode, ja que ens permet tindre un editor d'arxius i una terminal oberta al mateix programa.

Per a instal·lar mkdocs al nostre ordinador, executarem la següent ordre des de consola (konsole per a Lliurex, PowerShell per a Windows, ...):

```sh
pip install mkdocs
```

!!!warning "Pip"
    Ja haurieu de tindre pip instal·lat de unitats anteriors, en cas contrari has d'instal·lar python3 i durant la seua instal·lació marcar l'opció d'instal·lar *pip* i agregar-lo al PATH. Pots descarregar python3 del següent enllaç, [https://www.python.org/downloads/](https://www.python.org/downloads/).

Una vegada instal·lat mkdocs, haurieu de ser capços d'executar la següent ordre a la consola:

```sh
https://www.python.org/downloads/
```

Obtenint una resposta semblant a la següent:

```bash
mkdocs, version 1.3.1 from /home/ferran/.local/lib/python3.10/site-packages/mkdocs (Python 3.10)
```

## Creació d'un nou projecte

Una vegada tenim mkdocs instal·lat, necessitem crear un nou projecte per a construir la nostra web. Per tal de començar un nou projecte, executem:

```sh
mkdocs new "nom del projecte"
```

## Estructura del projecte

Al crear un nou projecte, amb mkdocs, observareu que s'ha creat una estructura com la següent:

```
.
├── docs
│   └── index.md
└── mkdocs.yml
```

- L'arxiu **mkdocs.yml** és l'arxiu de configuració de tot el projecte.
- La carpeta **docs** contindrà els nostres documents en format markdown.
- L'arxiu **index.md** és un arxiu de mostra que es mostrarà en format web al accedir a l'arrel del lloc web.

Si et fixes, per una banda tindrem el contingut en markdown i per altra la configuració de com renderitzar aquest contingut.

!!!warning "Carpeta docs"
    Encara que per defecte els arxius en format markdown estan a la carpeta docs, anem a canviar esta configuració en apartats posteriors.

## Servim la web en local

Per a servir una web, necessitaríem un servidor web que ens allotjara la nostra web per tal de poder accedir de forma local o remota a través del navegador. mkdocs ens facilita aquesta tasca creant un servidor al nostre ordinador per tal que pugam previsualitzar els canvis abans de servir-ho en un servidor públic (accessible a través d'internet) o construir la nostra web per a publicar-la.

Per a servir la nostra web, simplement hau d'executar el següent comandament:

```sh
$ mkdocs serve
INFO     -  Building documentation...
INFO     -  Cleaning site directory
INFO     -  Documentation built in 0.06 seconds
INFO     -  [12:49:32] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO     -  [12:49:32] Serving on http://127.0.0.1:8000/
```

Ara accedirem a l'URL `http://127.0.0.1:8000/` i podrem veure la pàgina web per defecte:

![index_per_defecte](img/index_per_defecte.png)

!!!note "Index per defecte"
    Obriu al VSCode l'arxiu index.md i fixeu-vos com es correspon amb el que esteu veient a la web local. És a dir, s'està renderitzant el markdown en format web.

    Ara podeu introduir els canvis que desitgeu al vostre contingut, i en guardar, els canvis es reflectiran automàticament al navegador, sempre i quan, l'ordre mkdocs serve continue en execució. **La autorecàrrega es produeix sempre que modifiquem l'arxiu de configuració, el contingut dels arxius markdown o els arxius del tema.**

