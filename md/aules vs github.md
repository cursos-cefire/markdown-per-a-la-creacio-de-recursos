## 1. Aules o github

La publicació en cadascuna d'estes plataformes té els seus avantatges i els seus inconvenients, que passem a enumerar.

### 1.1. Aules

#### 1.1.1. Avantatges

- És més fàcil de publicar, sobretot si no domines el control de versions amb VSCode.
- Es pot publicar de forma privada, de forma que sols els teus alumnes podran accedir.

#### 1.1.2. Inconvenients

- Per a veure el contingut, s'hauran d'autentificar necessàriament a Aules.
- Per fer canvis a la publicació, hauràs de repetir el procés de fer el build en local, comprimir en zip, pujar el zip, descomprimir-lo a Aules i marcar l'index.html com a arxiu principal.

### 1.2. Github

#### 1.2.1. Avantatges

- Fer modificacions és molt més còmode, simplement fes el build i sincronitza amb el remot.
- Els alumnes o les persones interessades tenen la informació accessible a través de la web, sense necessitat d'enregistrar-se i autenticar-se a Aules.


#### 1.2.2. Inconvenients

- Configurar un nou repositori és més tediós la primera vegada que s'inicia.
- La web ha de ser pública, de forma que el que publiques serà accessible per qualsevol persona amb accés a internet.

## 2. Una possibilitat

Una possibilitat és combinar Aules i Github. 

A Aules pengem una etiqueta amb l'enllaç a la nostra web per a tot el curs i enviem un avís als nostres alumnes cada vegada que publiquem un nou tema o nou material.

Treballem en la web local i enviem al remot per a la seua publicació les versions revisades. Si detectem qualsevol errada, fem el canvi a l'arxiu markdown, fem el build i ràpidament publiquem el canvi (no cal revisió si estem segurs del resultat).