
# Introducció

En aquest apartat ens centrarem a construir una pàgina web estàtica utilitzant **mkdocs**. De nou, l'aspecte de la web vindrà determinat per plantilles, encara que en aquest cas els anomenarem temes. Continuem, per tant, amb la idea principal del curs, centrar-nos en el contingut i no tant en l'aspecte, que simplement el configurarem una vegada.

Una vegada construït el nostre lloc, aprendrem a allotjar-lo a Aules i en un apartat posterior l'allotjarem en un repositori de github, per tal que estiga disponible de forma pública a través d'internet.

Abans de començar amb el desenvolupament de l'apartat, explicarem breument què és mkdocs.

## Què és [mkdocs](https://www.mkdocs.org/)?

!!!note "mkdocs"
    Mkdocs és un generador de llocs web estàtics, pren com a entrada text escrit en markdown i utilitza dissenys predefinits per crear un lloc web estàtic. Podeu modificar l'aspecte del lloc, els enllaços, les dades que es mostren a la pàgina i moltes coses més.



# Creació de la web en local

## Instal·lació de Jekyll i configuració de l'entorn de treball

Per començar instal·larem Jekyll al nostre ordinador.

### Debian, ubuntu i derivats (Lliurex)

Executem sobre l'intèrpret d'ordres els següents comandaments.

```bash
sudo apt-get install ruby-full build-essential
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
gem install jekyll bundler
```

Comproveu que *jekyll* s'ha instal·lat correctament:

```code
$ jekyll -v
jekyll 4.2.1
```

### Windows

Per a instal·lar sobre un sistema Windows, tenim disponible un instal·lador a la següent adreça:

[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)

Baixeu l'ultima versió que incorpora **Ruby + Devkit** i executeu-la. En l'última pantalla de l'assistent d'instal·lació demana si voleu executar *ridk install*, que per defecte ve marcat per a executar-se. Escolliu l'opció 3 quan vos ho demane per una finestra del *cmd*.

Quan acabe d'instal·lar, obriu un *cmd* i executeu:

```code
gem install jekyll bundler
```

Quan acabe, comproveu que teniu *jekyll* correctament instal·lat.

```code
$ jekyll -v
jekyll 4.2.1
```

### Més informació

Si necessiteu més informació sobre la instal·lació de jekyll, la podeu trobar al següent enllaç [https://jekyllrb.com/docs/installation/](https://jekyllrb.com/docs/installation/)

## Clonació del repositori

El que anem a fer ara és portar el repositori de Github al nostre ordinador per a poder agregar codi, que una vegada provat, tornarem a pujar a Github. 

Per a portar el codi hem de clonar el repositori al nostre disc dur. Utilitzarem la pestanya de control de versions que incorpora el Visual Studio Code per a fer-ho[^1].

[^1]: La clonació també es pot dur a terme amb l'ordre "git clone URL", sempre i quan el git estiga instal·lat al sistema.

![VSCode Clonar Repositori](img/jekyll/clonar-vscode.png){width=3cm}

Ens demanarà el repositori a clonar, ahí peguem la URL del nostre repositori. La podem obtindre del nostre repositori.

\begin{figure}
\centering
\subfigure[Clonar repositori buit]{\includegraphics[width=0.5\linewidth]{./img/jekyll/clonar.png}}
\subfigure[Clonar repositori]{\includegraphics[width=0.3\linewidth]{./img/jekyll/clonar2.png}}
\caption{Clonació de repositoris}
\end{figure}

:::warning
En cas de no tindre git instal·lat, l'opció de clonar el repositori ens apareixerà deshabilitada. 

Es pot instal·lar amb **sudo apt install git** en sistemes basats en Debian.  

En sistemes Windows podeu visitar el següent [enllaç](https://github.com/git-for-windows/git/releases/download/v2.33.1.windows.1/Git-2.33.1-64-bit.exe)
:::

Amb el VSCode obert sobre el directori on tenim clonat el repositori, comprovem que existeix una carpeta oculta `.git`, per exemple fent un `ls -la` a la línia d'ordres.

![Comprovar repositori](img/jekyll/comprovar-repositori.png){width=0.5}

## Posada en funcionament de la web en local

Una vegada comprovat que el repositori està al nostre disc i que el tenim obert al VSCode, anem a crear una pàgina web amb jekyll. Obrim una terminal al VSCode (`Ctrl + \``) i introduim les següents ordres:

```bash
jekyll new .
```

Veureu que a l'explorador del VSCode es crea una estructura de directoris com la de la següent imatge.

![Estructura de directoris Jekyll](img/jekyll/estructura-jekyll.png){width=6cm}

Si volem veure la web al nostre navegador local, executem l'ordre següent. Això ens crea un servidor web al nostre ordinador sobre el port 4000. Accedim a ell fent `Ctrl + clic` sobre el link que ens mostra a la consola o escrivint l'adreça 127.0.0.1:4000 a un navegador web. 

```bash
bundle exec jekyll serve
```

Fem `Ctrl + c` sobre la consola per a parar l'execució del servidor web.

# Publicació a Github

## Afegim arxius al repositori local

Ens queda solament publicar la web que acabem de crear amb jekyll a Github. Per fer això, el que hem de fer és publicar els canvis del repositori local al repositori de github.

El primer pas serà afegir tots els arxius que hem creat amb jekyll al repositori local. Si s'heu fixat a l'explorador del VSCode apareix la lletra U (*untracked*) a l'esquerra de cada arxiu. Això indica que eixe arxiu no està inclòs al repositori. Anem, en la pestanya de l'equerra, a *Source Control* i afegim tots els canvis fent clic a `... -> Changes -> Stage all changes`[^2]. 

[^2]: Si preferiu utilitzar la consola, feu `git add .`.

![Afegim al repositori local](img/jekyll/add.png){width=12cm}

Amb això, veureu que la U ha canviat a A (*added*). En este moment sols ens falta *confirmar* que volem afegir els canvis al repositori. Ho fem fent clic a l'icona de *check* i després escrivim un missatge per a identificar esta confirmació[^3]. 

[^3]: En consola seria `git commit -m "Primera web amb jekyll"`.

![Confirmem els canvis](img/jekyll/commit.png){width=12cm}

Per a evitar que ens fallen els commits, anem a configurar el nostre nom i el nostre correu a la configuració de Git, amb les següents dues ordres, introduint les vostres dades corresponents:

```bash
git config --global user.email "El vostre correu"
git config --global user.name "El vostre nom"
```

Per últim ens falta pujar els arxius a Github.

## Pugem els canvis a Github

Sols ens falta pujar els canvis al repositori en Github per a que la web es publique. Ho fem amb un *Push*[^4].

[^4]: Per als que utilitzeu la consola, seria `git push`.

![Pujar els canvis a Github](img/jekyll/push.png){width=12cm}

El VSCode ens avisarà de que l'extensió Github (ja ve integrada sense necessitat d'instal·lar-la) vol iniciar sessió a Github per a guardar els canvis que hem fet en local. Li donem a permetre i s'iniciarà l'intercanvi del *token* en diversos passos entre el navegador i el VSCode. A partir d'este moment VSCode podrà accedir de forma segura al repositori remot. Si no teniu la sessió iniciada a Github, se us demanarà l'usuari i la contrasenya durant el procés. 

![Registrar-se en Github](img/jekyll/allow.png){width=8cm}

Si tot ha anat bé, veureu en l'apartat de comptes d'usuari (icona de baix a l'esquerra) de VSCode que esteu amb la sessió de Github iniciada i el repositori local s'haurà pujat a Github per a la seua publicació.

![Comptes d'usuari i sessions](img/jekyll/account.png){width=8cm}

Podeu comprovar que els arxius que hem creat en local, estan al nostre respositori web de Github. Aneu a *Settings* i en l'apartat Pages vos indicarà si la pàgina ja està publicada i la seua adreça, que serà **https://nom_organització.github.io**. Comproveu que ja podeu navegar per ella.

:::caution
Els arxius es poden modificar tant per web com en local, però recomanem fer-ho sempre al mateix lloc si no domineu bé el programa de control de versions *git*, ja que poden aparéixer conflictes que s'han de resoldre al modificar en llocs diferents. Si voleu modificar als dos llocs, feu sempre un *Pull* (portar canvia del remot al local) al repositori local abans de fer les modificacions en local i un *Push* (penjar canvis del local al remot) a l'acabar.
:::

\newpage

# Modifiquem el contingut

## Configuració principal

Si s'heu fixat en l'estructura del directori que ens ha creat Jekyll, veureu que té diversos arxius. Anem primer a configurar el lloc a través de l'arxiu **_config.yml**. Us resultarà familiar perquè es tracta d'un arxiu yaml dels que ja hem vist al llarg del curs. Comentarem alguna de les configuracions que hem de modificar, seran:

- title -> (Obligatori) Títol del lloc web
- email -> (Opcional) El vostre correu.
- description -> (Obligatori) Descripció.
- baseurl: "" -> (Obligatori) Ho deixem en blanc si publiquem en una organització, si ho fem a un repositori sobre el nostre usuari, posarem /nom_repositori
- url: "" -> (Obligatori) https://nom_organització.github.io
- twitter_username -> (Opcional) Usuari twitter per als enllaços de xarxessocials.
- github_username -> (Opcional) Usuari Github per als enllaços de xarxessocials

:::note
Per als opcionals podem eliminar la línia, millor que deixar-ho en blanc.
:::

La part del tema recomanem no tocar-la, ja que les nostres pàgines tenen un *layout* ja definit. Si definim als arxius de contingut un layout que no existeix al tema, no es mostrarà res. 

## Tema i *layouts*

El tema mínima ja ve inclòs a Github i instal·lat quan creem una pàgina amb *jekyll new*. La resta de temes disponibles a Github els podeu consultar següent enllaç:  
[https://pages.github.com/themes/](https://pages.github.com/themes/).

- theme: minima

Els layouts són les diferents plantilles per a mostrar els continguts. Mínima inclou els layouts per a *default, home, page i post*. Si voleu canviar alguna cosa dels *layouts* de *minima*, aneu a la [web del tema](https://github.com/jekyll/minima), baixeu el repositori amb *git clone* i copieu-se la carpeta _layouts al vostre repositori. Dins de la carpeta podreu veure i modificar els layouts que ja porta incorporats. Feu les proves sempre en local i després pengeu el resultat final a github.

## Pàgines

Si es fixeu en l'arxiu *about.markdown* veureu que al *front matter* té un layout de pàgina, un títol i un permalink. Això li indica que es renderitzarà utilitzant el layout de pàgina, amb el titol indicat i que el link serà *https://proves-jekyll.github.io/about/* i no *https://proves-jekyll.github.io/about.html*. Després ja ve el contingut, que està en markdown.

Per a crear una nova pàgina, definirem *title:* i *layout: page*. Després insertarem el contingut en format markdown que ja coneixem.

```yaml
---
layout: home
title: Benvinguts a la web del curs de Markdown per a la creació de recursos
---
```

## Posts

A la carpeta _posts és on estan definits els posts. Per crear un post, hem de crear un arxiu amb la següent nomenclatura ANY-MES-DIA-titol.md. Per exemple:

2021-10-28-benvinguts-a-jekyll.markdown

Al front matter definim el títol, el layout, les categoris (opcional) i la data. Després insertem el contingut en markdown.

```yaml
---
layout: post
title:  "Benvingut a Jekyll!"
date:   2021-10-30 10:47:54 +0200
categories: jekyll
---
```

## Enllacem arxius locals a la web

Per a enllaçar arxius i posar-los a disposició dels usuaris de la nostra web utilitzarem les [variables de Jekyll](https://jekyllrb.com/docs/variables/). En este cas la que ens interessa és ***site.url***, però pots utilitzar altres per a diferents usos.

### Pengem arxius per a descàrrega 

Crearem una carpeta on allotjar els fitxers disponibles per a descàrrega i els enllaçarem amb un *link*. En el lloc web d'exemple, hem penjat un arxiu *2021-10-31-arxius-per-a-descarrega.pdf* a la carpeta *download*. Conté el contingut del post però en pdf. Així, per a enllaçar des d'un post o una pàgina quedaria com a continuació:

```md
---
layout: post
title: "Descarreguem arxius!"
date: 2021-10-31 11:31 +0200
categories: jekyll
---

## Descarrega d'arxius en Jekyll

Fes clic [ací]({{ site.url }}/download/2021-10-31-arxius-per-a-descarrega.pdf) per descarregar l'arxiu.
```

### Insertem imatges locals

Per a insertar imatges allotjades a una web simplement posem l'enllaç a la web externa, però si es tracta d'imatges locals, actuarem igual que en l'apartat anterior. Creem una carpeta on allotjar els nostres recursos i l'enllaçarem.

A la web d'exemple, hem creat una estructura de carpetes:

```
.
├── resources
    └── img
```

Hem allotjat dins una imatge i hem creat un post molt simple amb la imatge enllaçada:

```md
---
layout: post
title: "Imatges!"
date: 2021-10-31 11:45 +0200
categories: jekyll
---

## Insertem imatges locals

![Imatge de prova](/resources/img/portada.png)
```

## Canviem l'aspecte

A banda de poder canviar l'aspecte de la web a través del tema , que insistim  en no canviar fins que no dominem més les ferramentes, també podem canviar el fulls d'estils incorporant codi CSS o SASS. Teniu més informació al següent enllaç [https://jekyllrb.com/docs/assets/](https://jekyllrb.com/docs/assets/).


# Construim el lloc web completament

També tenim l'opció de construir un lloc completament funcional per poder-lo penjar a qualsevol altre servidor web, per exemple a Aules o Moodle. Per fer-ho, la única cosa que hem de fer és executar l'ordre:

```bash
jekyll build
```

Quan acabe d'executar-e veureu que jekyll ha creat una carpeta _site. Es tracta d'un lloc completament funcional que podeu penjar. Per fer-ho, comprimiu la carpeta a un arxiu .zip i el pengeu a aules, sense tancar la finestra de pujar l'arxiu, feu clic i a descomprimir. Després definu *index.html* com a arxiu principal[^5].

[^5]Mireu el final del vídeo on s'explica *Hugo* per a veure com es fa si teniu dubtes.

# Formes de treballar

Ja hem vist que construir la web tant en local com a github és molt senzill. Aleshores, recomanem treballar en local, agregar els canvis al repositori local i executar el servidor local. Comprovar que el resultat és el desitjat i en cas de ser-ho, penjar-ho al repositori de Github. Posteriorment, comprovar el resultat a Github. 

Si es tracta solament d'afegir o modificar una pàgina o un post es pot fer directament online perquè és extremadament fàcil i es pot fer des de qualsevol lloc amb accés a internet sense la necessitat de instal·lar res, però recordeu fer un *Pull* abans de començar a treballar en local la següent vegada.

Podeu utilitzar el control de versions per a tirar enrere alguns canvis, provar canvis a noves branques, etc. Esta part quedaria fora de l'abast del curs, però ho pots aprofitar si ja coneixes el funcionament de Git.

Podeu veure la pàgina web que hem creat com a exemple a l'adreça [https://proves-jekyll.github.io/](https://proves-jekyll.github.io/).

També la podreu veure al moodle del cefire (hem pujat _site tal com s'explica a este document i al vídeo de *Hugo*).

\newpage
# Resum

1. Creem usuari a github
2. Creem un lloc local amb `jekyll new`.
3. Servim el lloc construit amb `bundle exec jekyll serve`.
4. Fem les modificacions en local i mirem el resultat a `http://127.0.0.1:4000/`.
5. Pugem els canvis a Github i mirem el resultat en remot a `https://*organització*.github.io/`.ç  
6. Si voleu penjar a aules construim el lloc amb `jekyll build`.  
   1. Comprimim `_site` i el pengem com a arxiu a aules/moodle.
   2. Descomprimim i marquem `index.html` com a arxiu principal.