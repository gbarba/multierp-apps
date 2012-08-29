multiERP-Apps
=============

A Module Market-like application for Tryton and OpenERP, inspired in
apps.openerp.com.
It also take insipiration from Wordpress Extensions page and Debian package
organization (repositories, mantainer figure...).

Aplicació web que permet **explorar** els mòduls disponibles per diferents
versions d'OpenERP i Tryton (¿un mòdul pot ser per diverses versions o són
*llistats separats*? ¿quines versions de servidor tractem: minor o major?).

El sistema complementa la *metainformació* dels fitxers __tryton__.py i
__openerp__.py amb dades extra que genera ell mateix, que complementen els
mantenidors (veurem que hi ha mantenidors de mòduls) o que generen els propis
usuaris a partir *d'eines socials*. Aquesta informació extra, a més d'enriquir
la fitxa del mòdul, genera noves formes d'explorar els mòduls (per popularitat,
per compatibilitat...) i busca potenciar (visibilitzar) els autors en un
context de **meritocràcia**.

El sitema **suporta branques** pels mòduls i el servidor; diferents *versions*
d'un mateix codi. Aquestes tenen associats Sistemes de Control de Versions
(VCS), fitxers de *releases* (.egg, .zip...) i/o webapps de gestió de projectes
(github, bitbucket...).

Els usuaris poden afegir **informació de compatibilitat** entre branques de
mòduls i de servidor, i entre branques d'un mòdul i les seves dependències.

El sistema facilita **obtenir el codi complet** (fer un desplegament) de
servidor i mòduls (o d'una selecció de mòduls) seleccionant les branques
prioritzant diferents criteris: oficial, recomanat, màxima compatibilitat,
popularitat...

Per operar amb el sistema i explotar totes les funcionalitats, a més de la
interficie web el sistema **oferirà una API** i un **client per línia de
comandes**.

Tot el projecte és Software Lliure. Llicència ¿GPL3?


Contribute!
-----------

This project is currently in **specification** step and is **open to
contribution**.
You could find the working documents of specification in **doc** directory:

* *FeaturesAndRequirements.rst*: Specification of the Features and Requirements
  of the system from a User prespective.
* *Especificacio.rst*: this file is the previous version of specification, in
  Catalan. It will be deprecated.

**Send me your comments** about project and specification into my e-mail
(guillem@nan-tic.com), my Twitter (@wallas85) or in the Wiki page of this
project.


