=======================
Features & Requirements
=======================

.. contents::


Module Management
=================

.. image:: https://github.com/gbarba/multierp-apps/raw/master/doc/diagrams/module_branch_management_diagram.png

#. Each module has **an user assigned as *mantainer*** (required). He/She is
   responsible to mantain the information about module **correctly** and
   **completly**.

   #. Only the *site mantainers* can replace the *module mantainer* (as it is
      required, it must to be replaced, not removed)
   #. There is a **control (or opinion) mechanism** about *mantainer* to allow
      users to *force* the *Site Mantainers* to consider to replace a
      *mantainer* (because he/she aren't doing his work or is doing bad):
      #TODECIDE comments and/or votes over the mantainer (associated to the
      user or to the user+module), *abuse* report...
   #. A *mantainer* can ask to be replaced

      #. #TODECIDE if a mantainer propose a user to replace him, the
         substitution is automatic

#. A module could be deactivated (as in OpenERP, it's like deleted but
   mantaining the data in the system)

#. There is Server Versions which are as the *series* of Launchpad for all
   modules

   #. #TODECIDE: a module can be for multiple versions or server modules are
      different?
   #. #TODECIDE: Which server versions have their own serie: minor or **major**

#. A module has one or more branches (see `Branch Management`_) which are
   mantained by *module mantainer* and *branch mantainer*.

   #. If a module doesn't has any branch (because they has been
      deleted/deactivated) it's state changes to *warning* and an *advice* is
      sent to the mantainer
   #. The modules have a **default branch** (required if there is some branch)
      which is selected by the *mantainer* under his own criteria.

      #. If the *default branch* is deleted/deactivated, the module state
         change to *warning* (#TODECIDE the same or diferent than if it has no
         branches?) and an *advice* is sent to the mantainer

#. An User can register a new module. He/she will be the *mantainer*

   #. #TODECIDE: It requires validation? it depends on the *user status*
      (something like *commiters group*, based on Karma...)
   #. It's required to set up a branch when register a new module. This branch
      will be the *default branch* automatically

#. There is Server Versions which are as the *series* of Launchpad for all
   modules

   #. #TODECIDE: Which server versions have their own serie: minor or **major**
   #. #TODECIDE: a module can be for multiple versions/series (if not, for each
      Server Version a new module must to be registered)

      #. there is a *default branch* for each serie
      #. there is a *default serie* for the module


Branch Management
-----------------

The branches represents a version of a module. It could be a fork of existent
version (bugfixing) or a new version (improvement, extension)

#. A branch has this fields: #TODECIDE: Which of all of them are required
   fields?

   #. Version Number, Server Version Number and Creator User

      #. The Version Number will be updated

   #. #TODECIDE: Recomended Server Branch

      #. The Recomended Server Branch is set by the creator of module but it
         also could be changed by the Module Mantainer
      #. When this field is modified by the *module mantanier* or *branch
         mantainer (creator)*, it generates an *advice* for the other one.

   #. Version Control System (VCS)

      #. #TODECIDE Supported VCS: git, hg, bzr, svn...

   #. Project Management System:

      #. #TODECIDE Supported PM Systems: github, bitbucket, trac...

   #. Package Repositories:

      #. A module could be associated to multiple PR
      #. #TODECIDE Supported PR: PyPi, apt...

   #. Release Files:

      #. Multiple files (file types) per release
      #. #TODECIDE Supported file types: .egg, .zip, .tar.gz
      #. The system has a permanent link to the last release for each module
         which has any release files.
      #. #TODECIDE The name of release file must to follow an structured format
         that includes the Version Number.

   #. Documentation URL.

   #. State: #TODECIDE: see the launchpad states

#. An User can register a new branch

   #. #TODECIDE: It requires validation? it depends on the *user status* (something like *commiters group*, based on Karma...)

#. The system periodically checks that all URLs don't crash and the version of
   different release systems (files, Package Repositories...) is the last
   version of the module.

   #. The system mark as *deprecated* each of these information that isn't
      correct: it disables the link or download system and reduce the
      punctuation of mantainer.



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
* Deployment: buildout


