# LMSGI_03

**XML, esquemes i vocabularis**

He eleborat l'arxiu XML a partir de una taula publicada pel SEPE on es relacionen els certificat de professionalitat de la familia professional d'Electricitat i Electrònica:

[https://www.sepe.es/contenidos/personas/formacion/certificados_de_profesionalidad/electricidad_electronica.html#](https://www.sepe.es/contenidos/personas/formacion/certificados_de_profesionalidad/electricidad_electronica.html#)

A aquesta taula he afegit el camp hores per cada certificat.

Per crear i editar els arxius XML, DTD i XSD he fet servir l'aplicació [XML Copy Editor](http://xml-copy-editor.sourceforge.net/). També l'he feta servir per validar l'XML davant DTD i XSD.

## XML

L'estructura de l'arxiu XML seria:

* Element arrel: \<catalegcpele\>
  * Per cada certificat, amb una id: \<cp id="x"\>
    * Codi del cp (quatre lletres que identifiquen la familia i l'area + 4 digits): \<codicp\>ELEE0109\</codicp\>
    * Nivell del cp (pot ser de nivell 1 o 2 o 3): \<nivellcp\>1\</nivellcp\>
    * Nom del cp: \<nomcp\>Operaciones auxiliares de montaje de redes eléctricas\</nomcp\>
    * Durada del cp en hores: \<horescp\>220\</horescp\>
    * Url de la fitxa informativa del cp: \<urlcp\>https://www.sepe.es/contenidos/../fichasCertificados/ELEE0108_ficha.pdf\</urlcp\>
    * Reial Decret que regula el cp \<rdcp\>RD 1214/2009\</rdcp\>
  * Tancam etiqueta \</cp\>
  * Es torna a obrir etiqueta \<cp id="x+1"\>, definint les anteriors etiquetes (codicp, nivellcp, nomcp, horescp, urlcp, rdcp) per a cada cp. Tancam etiqueta cp, tornant a repetir el cicle.
* Tancam element arrel: \</catalegcpele\>

Un cop elaborat XML he comprovat que estigui ben escrit o format, fent servir [https://www.truugo.com/xml_validator/](https://www.truugo.com/xml_validator/):

![VALIDACIÓ XML](https://github.com/bielalzina/LMSGI_03/blob/master/imatges/xml_validation_well_formed.png?raw=true)

## DTD

Un cop elaborat el DTD, l'he validat amb el propi XML Copy Editor:

![VALIDACIÓ DTD 1](https://github.com/bielalzina/LMSGI_03/blob/master/imatges/xml_validation_dtd_1.png?raw=true)

I també en [https://www.truugo.com/xml_validator/](https://www.truugo.com/xml_validator/):

![VALIDACIÓ DTD 2](https://github.com/bielalzina/LMSGI_03/blob/master/imatges/xml_validation_dtd_2.png?raw=true)

En aquest cas, he inclos el codi DTD en l'arxiu XML




