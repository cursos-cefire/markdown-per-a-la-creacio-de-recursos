## Què és un sistema de control de versions?

Per a entendre què és Github, necessitem conéixer dos conceptes relacionats:

- Sistema de control de versions
- Git

Un *sistema de control de versions* ajuda els desenvolupadors de contingut a rastrejar i gestionar els canvis que es produïxen en un projecte. És àmpliament utilitzat en el desenvolupament de programari, però el podem aplicar a altres àmbits, com l'àmbit docent, per a gestionar els nostres apunts. 

Anem a veure un exemple ...

Imaginem que som desenvolupadors que col·laborem en el desenvolupament de [WordPress](https://wordpress.com/es/). Si un dels desenvolupadors volgués treballar en una de les parts del codi de WordPress, no seria segur ni eficaç que editra directament el codi font "oficial".

En lloc d'això, el control de versions permet als desenvolupadors treballar amb seguretat mitjançant *ramificacions* i *fusions*.

Amb la ramificació, un desenvolupador duplica el codi font (anomenat repositori) al seu ordinador. Aleshores, el desenvolupador pot fer canvis en aquesta part del codi sense afectar la resta del projecte.

Una vegada el desenvolupador ha provat i aconsegueix que la seua part del codi funcione correctament, pot incloure els seus canvis al projecte, és a dir, fusionar aquest codi amb el codi font principal per fer-lo oficial.

El *sistema de control*, ens permet aleshores veure quins canvis s'han produït, revertir-los, incloure'ls, tornar a una versió anterior, ...

Un altre exemple de control de versions el podem observar en els documents de Google Suite. Per veure les diferents versions que tenim d'un document, podem accedir fent clic a l'enllaç on indica quan s'ha guardat la última modificació que hem fet al document.

![GSuite: obrir control de versions](img/jekyll/control-version-gsuite.png)

Ens apareix una finestra on tenim les diferents versions que s'han anat guardant del document. També podem veure, en verd, què s'ha inclós al document des de les anteriors versions o què s'ha eliminat, esta vegada en verd però amb el text ratllat.

![GSuite: versions de document](img/jekyll/control-version-gsuite-2.png){width=14cm}

### Git

Git és un sistema de control de versions de codi obert creat per Linus Torvalds, el creador del primer kernel de Linux, l'any 2005.

Es diu que Git és un sistema de control de versions distribuït, ja que totes les versions estan disponibles a l'ordinador de cada desenvolupador, cosa que permet ramificar i fusionar molt fàcilment.

Segons una enquesta de desenvolupadors de Stack Overflow, més del 87% dels desenvolupadors utilitzen Git.

## Aleshores, què és [Github](https://github.com/)?

GitHub és una plataforma que ofereix un servei gratuït d'allotjament de repositoris Git basat en núvol. En altres paraules, és una forma d'utilitzar repositoris Git a través de la web.

La interfície de GitHub és molt intuïtiva i fàcil d'utilitzar, i elimina la necessitat d'utilitzar la línia de comandaments per a dur un control de versions. És tan fàcil d'utilitzar, que ha adquirit molta popularitat per a gestionar altres tipus de projectes, com ara escriure llibres, apunts...

Els repositoris que creem a Github poden ser públics i estar disponibles per a qualsevol persona o ser privats, però en aquest cas només seran accessibles pels col·laboradors del repositori.

:::note
Github va entrar en funcionament l'any 2008. 

L'any 2018, Microsoft el va adquirir per 7.500 milions de dòlars.

En Gener del 2020, GitHub tenia més de 40 milions d'usuaris, més de 190 milions de repositoris, 28 milions dels quals són públics.
:::

# Configuració de Github

## Registre d'usuari

En este primer punt, crearem un repositori github per a allotjar la nostra web. 

El primer pas serà registrar-nos a github en cas que no ho estigam ja accedint al següent enllaç [https://github.com/signup?user_email=&source=form-home-signup](https://github.com/signup?user_email=&source=form-home-signup).

:::warning
Fixeu-se que el registre es realitza a través d'un formulari completament integrat en la web amb una estètica molt cuidada
:::

![Registre de github](img/jekyll/github-register.png)

## Creació d'una organització

Una vegada estem registrats a github, iniciem la sessió i creem una nova organització amb el pla gratuït per a allotjar la nostra web. Per fer-ho, a la part de dalt a la dreta tenim l'opció per crear-la.

![Nova organització](img/jekyll/github-new-organization.png)

Per a accedir a les nostres organitzacions en qualsevol moment, ho farem a través del menú de l'usuari.

![Accedir a organització](img/jekyll/github-new-organization-2.png)

:::note
No cal crear una organització per a publicar la pàgina a Github, ja que també es pot publicar com a https://nom_usuari.github.com/nom_repositori. Si preferiu publicar ahí, aneu a l'apartat de *Settings* del repositori i en la pestanya *Pages* ho podreu configurar.
:::

## Creació d'un repositori

Per a crear un repositori, ho fem de forma semblant a la creació d'una organització, però esta vegada seleccionem crear un repositori en compte d'una organització. El fem public i no l'inicialitzem.

:::warning
Fixeu-se que en la creació del repositori ho podem fer sobre el nostre usuari o sobre les nostres organitzacions. Esta vegada utilitzarem la organització que acabem de crear.
:::

![Nou repositori sobre l'organització](img/jekyll/github-new-repository.png)

:::important
Per a poder publicar la nostra web és **imprescindible** que el nom del repositori siga *nom_de_l'organització.github.io*
:::

En l'exemple, l'organització és *proves-jekyll*, per tant, el repositori serà *proves-jekyll.github.io*

## Prova de la publicació

En estos moments ja tindries creada la teua web, però sense contingut. El que podem fer és crear un arxiu index.html per a comprovar que efectivament la nostra web està en funcionament.

Creem un nou document al repositori  que acabem de crear amb el botó *Add file*.

![Afegir document](img/jekyll/create-file.png)

S'obrirà un editor de text on esciurem el contingut que vulgam publicar. Assignem també un nom a l'arxiu.

![Editar index.html](img/jekyll/index.png)

En pocs segons es publicarà la web, a la que podem accedir escrivint a la barra de navegació del navegador web el nom del nostre respositori, *proves-jekyll.github.io* en el cas de l'exemple.

![Prova web](img/jekyll/web-prova.png)

Si la prova ha funcionat, podem eliminar el document *index.html*.
