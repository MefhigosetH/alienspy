```
******************************************************
   WARNING: COMPUTER MALICIUS EXECUTABLE CODE HERE!

   OPEN ON GNU/LINUX BASED PC ONLY - INFECTION HAZARD
******************************************************
```

# AlienSpy basic malware analysis

This paper will discuss a basic malware analysis exercise performed on an AlienSpy (seen in the wild) sample.

## Background

Natalio Alberto Nisman (5 December 1963 – 18 January 2015) was an Argentine lawyer who worked as a federal prosecutor, noted for being the chief investigator of the 1994 car bombing of the Jewish center in Buenos Aires, which killed 85 people, the worst terrorist attack in Argentina's history. On 18 January 2015, Nisman was found dead at his home in Buenos Aires.

There are proofs that he was targeted, a few days before his dead, by invasive spy software downloaded onto his cellular phone and PC shortly before his mysterious death. The software masqueraded as a confidential document and was intended to infect a Windows computer.

## Media

More info about the case, can be found on these links:

* [Alberto Nisman](https://en.wikipedia.org/wiki/Alberto_Nisman)
* [Malware hunter finds spyware used against dead argentine prosecutor](http://motherboard.vice.com/read/malware-hunter-finds-spyware-used-against-dead-argentine-prosecutor)
* [Nisman tenia en su celular un potente virus para espiarlo](http://www.lanacion.com.ar/1818409-nisman-tenia-en-su-celular-un-potente-virus-para-espiarlo)
* [Inside the spyware campaign against argentine troublemakers including Alberto Nisman](https://firstlook.org/theintercept/2015/08/21/inside-the-spyware-campaign-against-argentine-troublemakers-including-alberto-nisman/)

## About the analysis

The analysis is divided into the following folders:

* **evidence**: Contain the source code of mail used tu send the malware sample.
* **surface_analysis**: Examines the structural properties and file attributes of the malware sample: true file type, size, file hash values, etc.