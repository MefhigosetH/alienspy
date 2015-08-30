```
******************************************************
   WARNING: COMPUTER MALICIUS EXECUTABLE CODE HERE!

   OPEN ON GNU/LINUX BASED PC ONLY - INFECTION HAZARD
******************************************************
```
# AlienSpy basic malware surface analysis

A surface analysis examines the structural properties and file attributes of a malware sample (True file type, size, file hash values, file and section headers, strings, contained objects, packing mechanisms) without viewing assembly or machine-level instructions. Surface analysis can provide information artifacts (such as IP address, Internet domain names, and command parameters) that prove useful in subsequent analysis steps.

## Surface analysis for 'Estrictamente Secreto y Confidencial.pdf.jar' file

Inside `evidence` folder there is a file named `email.txt` . This is the source code of the e-mail used to send the malware sample.

First extract the attached file from the email:

    $ ripmime -i email.txt -v -d /tmp/
    Decoding filename=Estrictamente Secreto y Confidencial.pdf.jar

Now we have a file with the following attributes:

> * **Filename**: "Estrictamente Secreto y Confidencial.pdf.jar"
> * **Size**: 67126 Bytes.
> * **SHA256**: aa9aa05af8df2cc99eb936e2d17623a68abdbb60606bb097379457c4a3760116
> * **FileType**: Zip archive data, at least v2.0 to extract

After unzip this file we have the following directory tree:

    Estrictamente Secreto y Confidencial.pdf.jar
    |____ META-INF
    |   |____ MANIFEST.MF
    |____ Favicon.ico
    |____ Principal.class

With the following attributes:

> * **Filename**: "META-INF/MANIFEST.MF"
> * **Size**: 200 Bytes.
> * **SHA256**: 405e59172ba3418409ef5cddd3d033654adacb3ecabac9c50de2008857da1092
> * **FileType**: ASCII text, with CRLF line terminators

----------

> * **Filename**: "Favicon.ico"
> * **Size**: 62562 Bytes.
> * **SHA256**: 83a9314afe3f33da29abb377f3395ce9c0eb4cf36170dd0d60046477286481a0
> * **FileType**: Zip archive data, at least v2.0 to extract

----------

> * **Filename**: "Principal.class"
> * **Size**: 4541 Bytes.
> * **SHA256**: c188daeeca97d4c2f9a58114cff410f1fc69399a6543644ad62cd06ea239ccf0
> * **FileType**: compiled Java class data, version 50.0 (Java 1.6)

----------

The contents for `META-INF/MANIFEST.MF` file are:

    Manifest-Version: 1.0
    Ant-Version: Apache Ant 1.9.1
    X-COMMENT: Main-Class will be added automatically by build
    Class-Path: 
    Created-By: 1.7.0_25-b17 (Oracle Corporation)
    Main-Class: Principal

Note the size and filetype of the `Favicon.ico` file. This is our next goal.

## Surface analysis for 'Favicon.ico' file

After unzip this file we have the following directory tree:

    Estrictamente Secreto y Confidencial.pdf.jar
    |____ 0doc.jar
    |____ 1Estrictamente Secreto y Confidencial.pdf

With the following attributes:

> * **Filename**: "0doc.jar"
> * **Size**: 55381 Bytes
> * **SHA256**: db823637711d2946deccdbfde172c4f38dc6cb83d9575fb30802aab3687d3a9d
> * **FileType**: Zip archive data, at least v2.0 to extract

----------

> * **Filename**: "1Estrictamente Secreto y Confidencial.pdf"
> * **Size**: 8134 Bytes
> * **SHA256**: 1d25194442f24a2c996d2f8952c9776675ce6f69f33a517fab72616d640de60c
> * **FileType**: PDF document, version 1.4

----------

The `1Estrictamente Secreto y Confidencial.pdf` has the following metadata:

    Title:          Microsoft Word - Documento1
    Author:         USER
    Creator:        PScript5.dll Version 5.2.2
    Producer:       GPL Ghostscript 8.15
    CreationDate:   Mon Dec  1 12:28:38 2014
    ModDate:        Mon Dec  1 12:28:38 2014
    Tagged:         no
    Pages:          1
    Encrypted:      no
    Page size:      842 x 1191 pts (A3)
    File size:      8134 bytes
    Optimized:      no
    PDF version:    1.4

JavaScript or malicius code not found on this PDF file.
