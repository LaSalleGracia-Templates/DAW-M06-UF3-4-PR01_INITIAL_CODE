# **DAW-M06-UF3-4-PR01_INITIAL_CODE**
Repositori del codi inicial de la pràctica 1 del M06-UF3 i 4 (JS bàsic)

# **Instruccions**
- És necessari superar una entrevista o presentació de la pràctica mostrant el correcte funcionament de l'aplicació per poder obtenir una nota.
- L'entrega es realitzarà utilitzant 2 plataformes: Sallenet i Github. És obligatoria l'entrega dins del termini a les dues per poder obtenir una nota.
- És obligatori que hi hagi mínim 4 commits en el repositori (un commit per classe).
- La pràctica es realitzarà en parelles cada parella ha de fer un mínim de 2 commits.

# **Enunciat**
## **LS PokeMemory**
Se'ns demana crear una aplicació similar a un joc del Memory utilizant imatges de pokemons.

##* **Instruccions del joc Memory simple**
L'usuari té X parelles de cartes girades cap per avall sobre el tauler (on X és un nombre natural qualsevol).
Quan l'usuari clica a una carta, aquesta es gira i es mostra la imatge de la cara superior. Al clicar a una segona carta, si no té la mateixa imatge que l'anterior, es tornen a girar cap per avall les dues cartes, si té la mateixa imatge que l'anterior, es mantenen destapades i ja no es poden tocar més aquestes dues cartes.
Quan l'usuari ha destapat totes les cartes (ha trobat totes les parelles guanya).

### **Interaccions de l'usuari del PokeMemory**
1. Al principi l'usuari veurà només un formulari de registre amb id "registerForm". En aquest formulari se li demanarà les següents dades amb els següents inputs HTML:
  - Username: amb un input HTML amb id "username".
  - Email: amb un input HTML amb id "email".
  - Age: amb un input HTML amb id "age".
Quan l'usuari cliqui al botó submit del formulari, s'haurà de:
  1. Validar que els inputs HTML compleixin les següents condicions:
    - Username: ha de ser un string que només permeti lletres (majúscules i minúscules) i espais.
    - Email: ha de ser un string amb format de email (un text alfanumèric +  una "@" + un text alfanumèric + "." + un text alfanumèric).
    - Age: ha de ser un nombre enter major que 0 i menor que 150.
  2. Utilitzant l'API i la BBDD "Realtime DB" que ofereix l'aplicació de Firebase (fent servir el mètode "fetch", no la llibreria de Firebase) cal comprovar si el email existeix a la BBDD.
    - Si existeix, s'ha de sobreescriure el username.
    - Si no existeix, s'ha d'afegir un nou registre.
  3. L'id d'usuari que retorni l'API s'haurà de guardar al sessionStorage amb la clau "user".
2. Sempre que hi hagi un id d'usuari amb la clau "user" al sessionStorage, no es mostrarà el formulari de registre, sino que es mostrarà la vista del joc.
3. La vista del joc consistirà en 3 parts:
  1. Al costat esquerra es mostrarà el següent:
    - Un formulari amb id "gameForm" per introduir quantes cartes l'usuari vol que tingui la partida.
      - Per fer-ho tenir un input HTML amb id "numCards".
      - Quan es cliqui al botó de submit del formulari, caldrà verificar si a l'input hi ha un nombre enter, positiu i parell.
      - Si és correcte, començarà la partida:
        - S'iniciarà un contador amb id "timer", en el que es veuran els minuts i segons.
        - Es mostrarà el taulell del joc amb les cartes girades.
        - No cal crear l'efecte de girar una carta. Al clicar-ne una, es pot mostrar la imatge.
        - Quan l'usuari hagi trobat dues cartes iguals, s'han de marcar amb el color verd de background.
        - Per obtenir les imatges dels pokemons es farà servir l'API "pokeapi".
  2. Al costat dret (ranking)
  3. Un botó amb id "logout" per eliminar l'id guardada al sessionStorage i recarregar la pàgina.

