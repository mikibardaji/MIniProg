# Diccionari de dades App Inventor

## Objectiu

Aprendre què és un **diccionari de dades** i com serveix per guardar i recuperar informació estructurada, com la fitxa d'un alumne.

Cada element té una *clau*:

      - nom
      - edat
      - curs
i un *valor*:

      - Laura
      - 18
      - 2n SMX

## Disseny de la pantalla

Components principals:
* Label (lblTitol): 'Diccionari de dades - Ficha d'alumne'
* TextBox (txtNom): Nom de l'alumne
* TextBox (txtEdat): Edat
* TextBox (txtCurs): Curs (ex: 2n SMX)
* Button (btnGuardar): Guardar dades
* Button (btnMostrar): Mostrar dades
* Label (IblResultat): resultat final
* Label (IblJson): resultat final

<center>
<img src="pantallaDiccionari.PNG" alt="Text alternatiu" >
</center>

## Crear el diccionari

**Variable global:**
* `initialize global dicAlumne to create empty dictionary`

**Quan es clica *Guardar dades*:**
* `set global dicAlumne to create empty dictionary`
* `call dictionary set value (dicAlumne, 'nom', txtNom.Text)`
* `call dictionary set value (dicAlumne, 'edat', txtEdat.Text)`
* `call dictionary set value (dicAlumne, 'curs', txtCurs.Text)`

<center>
<img src="botoGuardar.PNG" alt="Boto Guardar Codi" >
</center>

## Mostrar les dades

* **Quan es clica *Mostrar dades*:**
    `set IblResultat.Text to join (`
    `'Nom: ' + dictionary lookup(dicAlumne, 'nom', '') + '\n' +`
    `'Edat: ' + dictionary lookup(dicAlumne, 'edat', '') + '\n' +`
    `'Curs: ' + dictionary lookup(dicAlumne, 'curs', '')`
    `)`

<center>
<img src="botoMostrar.PNG" alt="Boto Guardar Codi" >
</center>


## Versió avançada: format JSON

Afegir un label (lblJson): Per veure com es poden guardar amb un format mundialment reconegut.

Al mateix boto Mostrar, es passara el dictionary a aquesta Jlabel

<center>
<img src="mostrarJson.PNG" alt="Boto Guardar Codi" >
</center>

El JSON és el format que usen les apps reals per compartir dades.

## Extensió opcional

* **Guardar diversos alumnes en una llista de diccionaris:**
* `initialize global diccionari_alumnes to create empty dictionary`
* `initialize global llistaAlumnes to create empty list.`

<center>
      <img src="llistaalumnes.PNG" alt="Boto Guardar Codi" >
</center>

  
* Crear una variable local dictionary per exemple `local_alumne` inicialment a `empty dictionary` e, informar Tots els camps amb dictionari LOCAL, després passar-lo a la llista.

<center>
      <img src="botoMostrarLlistaDictionaris.PNG" alt="Boto Guardar Codi" >
</center>

[Imatge dels blocs d'App Inventor per a l'extensió opcional (crear local_alumne)]

* Despres `add items to list (llista Alumnes, local_alumne)`

[Imatge dels blocs d'App Inventor per "add items to list"]

* Això equival a tenir una taula de base de dades amb diversos alumnes.
