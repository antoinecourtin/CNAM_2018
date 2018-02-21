## Template pour exporter fixhier CSV en XML-EAD à plat
#### Exo pour formation AAF



* A mettre dans **Prefix**
```
<?xml version="1.0" encoding="UTF-8"?><?xml-stylesheet type='text/css' href='ead.css'?>
<ead>
 <eadheader countryencoding="iso3166-1" dateencoding="iso8601" findaidstatus="acheve" langencoding="iso639-2b" relatedencoding="DC" repositoryencoding="iso15511" scriptencoding="iso15924">
  <eadid>FRAD_IR_???</eadid>
  <filedesc>
   <titlestmt>
    <titleproper>TITRE de l'IR</titleproper>
    <author>par OpenRefine :-)</author>
   </titlestmt>
   <editionstmt>
    <edition>Première édition électronique</edition>
   </editionstmt>
   <publicationstmt>
    <publisher>Archives de l'AAF </publisher>
    <address>
     <addressline>Paris</addressline>
    </address>
    <date calendar="gregorian" era="ce" normal="2014-01-01/2014-12-31">2014</date>
   </publicationstmt>
  </filedesc>
  <profiledesc>
   <creation>Cet instrument de recherche a été généra par OP !</creation>
   <langusage>
    <language langcode="fre">Il est en français.</language>
   </langusage>
   <descrules>Conforme à la norme ISAD(G) et aux règles d'application de la DTD EAD (version 2002) aux Archives nationales, il a reçu le visa du Service interministériel des Archives de France le .....</descrules>
  </profiledesc>
 </eadheader>
 <archdesc level="recordgrp">
  <did>
   <unitid countrycode="fr" repositorycode="FRDAFAN" type="identifiant">20140297/1-20140297/23</unitid>
   <unittitle>Fonds de carte postale de test</unittitle>
   <unitdate calendar="gregorian" era="ce" normal="1929-01-01/1959-12-31">1929-1959</unitdate>
   <origination>
    <corpname authfilenumber="FR_">Archives de l'AAF </corpname>
   </origination>
   <physdesc>
    <extent>0,3ml (1 carton) soit 23 chemises</extent>
   </physdesc>
   <langmaterial>
    <language langcode="fre">français</language>
   </langmaterial>
   <repository>Archives nationales</repository>
   <physloc>Dans mon bureau</physloc>
  </did>
  <accessrestrict>
   <p>Les documents sont librement communicables</p>
  </accessrestrict>
  <userestrict>
   <p>Selon règlement de la salle de lecture</p>
  </userestrict>
  <dsc>
```

* A mettre dans **Row template**

  ```
  <c>
   <did>
      <unitid> {{jsonize(cells["cote"].value)}}</unitid>
      <unititle>{{jsonize(cells["TITRE"].value)}}</unititle>
      <unitdate>{{jsonize(cells["DATE"].value)}}</unitdate>
    </did>
    <controlaccess>
      <persname role="auteur">{{jsonize(cells["NOM"].value)}}</persname>
      <geogname>{{jsonize(cells["VILLE"].value)}}</geogname>
    </controlaccess>
  </c>
  ```

  * A mettre dans **Suffix**

  ```
  </dsc>
  </archdesc>
  </ead>
  ```
