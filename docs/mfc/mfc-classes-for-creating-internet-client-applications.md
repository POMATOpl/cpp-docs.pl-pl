---
description: 'Dowiedz się więcej na temat: klasy MFC do tworzenia aplikacji internetowych klienta'
title: Klasy MFC do tworzenia klienckich aplikacji internetowych
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, WinInet classes
- WinInet classes [MFC], classes
- classes [MFC], MFC
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
ms.openlocfilehash: c68110182b01d9c425090a926ee1e352ca3d3bdf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280680"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>Klasy MFC do tworzenia klienckich aplikacji internetowych

MFC udostępnia następujące klasy i funkcje globalne do pisania aplikacji internetowych klientów. Wcięcie wskazuje, że Klasa pochodzi od klasy bez wcięcia. `CGopherFile` i `CHttpFile` pochodzić z `CInternetFile` , na przykład. Te klasy i funkcje globalne są deklarowane w AFXINET. H, z wyjątkiem `CFileFind` , który jest zadeklarowany w AFX. H.

## <a name="classes"></a>Klasy

- [CInternetSession](reference/cinternetsession-class.md)

- [CInternetConnection](reference/cinternetconnection-class.md)

  - [CFtpConnection](reference/cftpconnection-class.md)

  - [CGopherConnection](reference/cgopherconnection-class.md)

  - [CHttpConnection](reference/chttpconnection-class.md)

- [CInternetFile](reference/cinternetfile-class.md)

  - [CGopherFile](reference/cgopherfile-class.md)

  - [CHttpFile](reference/chttpfile-class.md)

- [CFileFind](reference/cfilefind-class.md)

  - [CFtpFileFind](reference/cftpfilefind-class.md)

  - [CGopherFileFind](reference/cgopherfilefind-class.md)

- [CGopherLocator](reference/cgopherlocator-class.md)

- [CInternetException](reference/cinternetexception-class.md)

## <a name="global-functions"></a>Funkcje globalne

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>Zobacz też

[Rozszerzenia internetowe Win32 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[Wymagania wstępne dotyczące klas klientów internetowych](prerequisites-for-internet-client-classes.md)<br/>
[Pisanie aplikacji klienckiej internetowej przy użyciu klas MFC WinInet](writing-an-internet-client-application-using-mfc-wininet-classes.md)
