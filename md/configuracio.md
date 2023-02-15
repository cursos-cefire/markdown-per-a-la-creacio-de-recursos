# Configuració

## Modifiquem l'arxiu *mkdocs.yml*

### site_name

L'única configuració que és necessària per a servir la web és el *site_name*, que serà una cadena de text que definirà el títol de la pestanya del navegador i apareixerà en el menú de navegació. Diriem que és el nom que defineix la nostra web, per tant serà la primera configuració que modificarem.

Per exemple, en el cas d'esta web, hem posat com a *site_name: Web estàtica amb mkdocs*

## Pàgines

Anem a veure en este apartat com configurar noves pàgines a la nostra web. Seran accessibles a través del menú de navegació.

El primer pas serà incorporar un nou arxiu .md amb contingut, per exemple, about.md a la carpeta docs.

Després modificarem l'arxiu de configuració per afegir al menú de navegació les nostres pàgines de la forma següent:

```yaml
nav:
    - Home: index.md
    - About: about.md
```
Ara la pàgina tindrà l'aspecte següent:

![pagines](img/pagines.png)

Pots observar que al menú de navegació ara tenim les opcions Home i About i també ens han aparegut unes fletxes de *Previous* i *Next* per poder navegar a través d'elles.

Es poden crear submenús al menú de navegació, configurant el *mkdocs.yml*:

```yaml
nav:
    - Home: index.md
    - Tema 1:
      - Apartat 1: tema1/apartat1.md
      - Apartat 2: tema1/apartat2.md
    - About: about.md
```

![submenus](img/submenus.png)

## Buscador

Observeu que també disposem d'un buscador al menú de navegació que ens permetrà buscar a través del contingut de la web. 

!!!note "Buscador" 
    Açò pot ser molt útil per als nostres alumnes a l'hora d'utilitzar els nostres recursos com a documentació de referència. Els permetrà localitzar ràpidament el contingut que busuqen.

    Observeu que ens trobarà totes les ocurrències del contingut buscat.

## Tema

Fins ara, hem utilitzat el tema per defecte per a renderitzar la pàgina, però existeixen altres temes per canviar l'aspecte a la nostra web, sense haver de canviar res al nostre contingut.

Per canviar el tema, editem l'arxiu de configuració i afegim una línia com la següent:

```yaml
theme: readthedocs
```
En guardar l'arxiu, l'aspecte haurà canviat al del tema *readthedocs*:

![readthedocs](img/readthedocs.png)

!!!info "Temes per defecte"
    Mkdocs sols incorpora dos temes, mkdocs i readthedocs, però hi ha temes desenvolupats per tercers que podeu utilitzar. Simplement s'hauria de mirar a la documentació corresponent com posar-los en funcionament. Sol ser un procés molt senzill. 

    Al següent enllaç tens informació sobre altres temes per a mkdocs, [https://github.com/mkdocs/mkdocs/wiki/MkDocs-Themes](https://github.com/mkdocs/mkdocs/wiki/MkDocs-Themes).

## Canviant l'icona de la nostra web

Per defecte, mkdocs utilitza la seua propia icona. Si volem utilitzar una icona diferent, crea un directori img a la carpeta docs i guarda una icona amb el nom favicon.ico, mkdocs el detectarà i el canviarà automàticament.

## Construim el lloc web

Finalment, després d'haver comprovat al nostre ordinador que el resultat és l'esperat, construïm el lloc web, és a dir, el deixem enllestit per poder-lo penjar a un servidor amb l'ordre:

```sh
mkdocs build
```

Veuràs que es crea una carpeta *site* amb l'estructura següent:

![site](img/site.png)

Esta carpeta conté tots els arxius necessaris per servir la web, i és la carpeta que publiquen els servidors per a accedir a les seues respectives webs.

# Resum

1. Instal·lem mkdocs.
2. Creem un nou projecte amb `mkdocs new "nom del projecte"`.
3. Servim el lloc en local i comprovem que tot va funcionant i es visualitza com desitgem amb `mkdocs serve`.
4. Afegim el contingut en arxius .md a la carpeta docs.
5. Enllacem els diferents arxius al menú de navegació modificant l'arxiu mkdocs.yml.
6. Configurem el tema, el nom del lloc i la resta de configuracions que vulguem utilitzar.
7. Construim el lloc amb `mkdocs build`.