=======================
Features & Requirements
=======================

.. contents::


Module Management
=================

.. image:: https://raw.github.com/gbarba/multierp-apps/master/doc/diagrams/module_branch_management_diagram.png

#. Cada mòdul **té un *mantenidor* assignat** (requerit). És l'encarregat de vetllar perquè la informació que figura al sistema respecte al mòdul sigui **correcta** i el més **completa** possible.

   #. Dóna d'alta (¿o només valida les altes que fa la gent?) noves branques... ***gestiona branques***
   #. Hi ha d'haver algun tipus de mecanisme de *control* (opinió) sobre el mantenidor per *forçar* a considerar de substituir-lo: comentaris i/o vots sobre la ficha del mantenidor (associats a l'usuari o al mòdul+usuari; mantenidor del mòdul en el moment del comentari)
   #. Els administradors del site tenen l'última paraula en la substitució de mantenidors de mòduls.

      #. ¿autosubstitució? avisos marcats de forma diferent per facilitar l'aprovació o directes sense aprovació

#. Un usuari pot donar d'alta un nou mòdul (¿cal validació? ¿condicionat al *status* de l'usuari rollo *commiters*) amb la seva branca (obligatori)

   #. Automàticament queda assignat com a mantenidor del mòdul i la branca com a *per defecte*

#. Un mòdul es pot desactivar (eliminar sense eliminar)
#. Un mòdul ha de tenir com a mínim una branca, però el camp no és requerit; si no té cap branca queda en estat *warning* (o algo així)
#. Un mòdul té una **branca per defecte** que la selecciona el *mantenidor* del mòdul al seu criteri

   #. Si la *branca per defecte* s'elimina o es desactiva ¿o es queda en *warning*?, el mòdul queda en estat *warning* (el mateix o diferent que si no té branques?)


Gestió de branques
------------------

Les branques representen una versió del mòdul, ja sigui un fork d'una existent o una nova (i única)

#. Un usuari pot donar d'alta una branca (¿cal validació? ¿condicionat al *status* de l'usuari rollo *commiters*)
#. Una braca té un *número de versió*, un *número de versió de servidor* i un *usuari creador*

   #. ¿opcionalment? una relació amb la branca de servidor recomanada

      #. La *Branca de servidor recomanada* l'estableix el creador però la pot canviar el mantenidor del mòdul. Això genera un avís al *mantenidor* en el primer cas, i al *creador* de la branca en el segón.

#. El número de versió pot anar-se actualitzant
#. opcional? Una branca té tipus i URL (o el mètode que toqui) de VCS (git, bzr, svn...)
#. opcional? Una branca té fitxers descarregables (zip, tgz...) i el sistema genera un link automàtic a l'últim

   #. ¿Forçar que el nom s'avingui a notació estructurada NOM_DEL_MODUL.VERSIO.EXTENSIÓ? ¿Cal una gestió de releases?

#. opcional? una branca té info per 'pip' i per altres gestors de paquets
#. ¿El *mantenidor* o *creador* poden marcar el *sistema* recomanat?
#. Marcar d'alguna forma cada *tipus* amb: *desenvolupament*, *llest per producció*, *release*, *stable*


Dependències del mòdul
----------------------

#. Un mòdul té un llistat de dependències
#. Una dependència té un mòdul objectiu
#. Una dependència té una branca de mòdul objectiu recomanada

   #. La gestiona el mantenidor de la branca i dels mòduls


User Profiles
=============

.. image:: https://raw.github.com/gbarba/multierp-apps/master/doc/diagrams/user_profile_diagram.png

#. Des del perfil d'usuari accedim a la llista de:

   #. Mòduls del que és *mantenidor*
   #. Branques de les que és *creador* (¿o també li diem *mantenidor*?)
   #. Mòduls (branques) del que *autor* (¿diferenciem *creador* de *autor*?). No té pq ser el mateix que l'anterior. Pots tenir una branca per manteir 4 canvis/bugfix però no considerar-te *autor*

#. El perfil té un històric que s'alimenta ¿d'*avisos* d'un(s) tipu(s) concret? que estan relacionats amb mòdul [i branca] per poder fer filtratges i tal. Els diferents *subtipus* (els següents exemples) també serien un camp per filtrar

   #. Exemple: Aquest usuari va ser autor d'aquesta branca (i per tant, mòdul) fins el X (quan es treu un *autor* d'un mòdul)

      #. ¿També quan s'afegeix? crec que no fa falta


Avisos
------

El sistema pot generar avisos a l'estil de les **notificacions** d'OpenERP. Van dirigides a un usuari i aquest té una *safata d'entrada*.
En principi no són missatges *usuari a usuari*, per tant tampoc hi ha *respostes*. Si s'habilités aquest tipus de missatges ¿fem que **puguin** ser públiques i series *Converses*? (això es pot fer amb fòrums o coses així)

#. Quan es genera algun *warning* s'envia un avís al mantenidor del mòdul.
#. L'usuari pot configurar si rep un e-mail quan rep un avís


Social Features
===============

.. image:: https://raw.github.com/gbarba/multierp-apps/master/doc/diagrams/social_functions_diagram.png


Comentaris a mòduls i branques
------------------------------

#. Els comentaris van associats a un mòdul i ¿opcionalment? a una branca

   #. Des del mòdul es pot veure l'arbre de comentaris complet
   #. Des de la branca es mostren dos pestanyes: comentaris de la branca (filtrats) i del mòdul (tots)
   #. #TODECIDE: Un arxiu de comentaris del mòdul **per branca**?
   #. #TODO: Discus permetria això?

#. #TODECIDE: Un comentari té etiquetes

   #. hi ha un arxiu de comentaris per etiqueta que permetria minifòrums pels mòduls


Compatibility Reports
---------------------

Based on how the Wordpress Extension Web resolves this question.

#. The reports are **between branches**, and specifying the version for each
   branch. The users which doesn't have this information aren't our target.
#. Types:

   * Between Module and its Server
   * Between Module and its dependencies
   * Between Modules (no dependant modules): this type probably will only be
     *no compability report*; the system must to take care about this.

#. The system will calculate and show the *average score of compatibility*, the
   *number of reports* and will assign a *flag* (red, yellow or green) taking
   care this two values.

   #. The system will be able to select the *most compatible branch* (for a
      module set) and advice about *compatibility problems*.

#. #TODECIDE: The author of report (User) is required (I think yes)? This info
   is private (not visible for anonymous, only for manainers, for anybody)?


Technology
==========

(the **bold** options are my preferences)

* WebApp

  * Flask
  * Django

* API

  * **RESTful + JSON**
  * XML-RPC

* Client: Python script


