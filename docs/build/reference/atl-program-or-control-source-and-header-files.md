---
description: Dowiedz się więcej o programie ATL lub źródłowym formancie i plikach nagłówkowych
title: Program ATL lub źródło kontroli i pliki nagłówkowe
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: 05407e74931112a1680fb103c20c4a2022185026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182791"
---
# <a name="atl-program-or-control-source-and-header-files"></a>Program ATL lub źródło kontroli i pliki nagłówkowe

Następujące pliki są tworzone podczas tworzenia projektu ATL w programie Visual Studio, w zależności od opcji wybranych dla tworzonego projektu.

Wszystkie te pliki znajdują się w katalogu *Projname* , a w folderze plików nagłówkowych (pliki. h) folderu lub pliki źródłowe (pliki. cpp) w Eksplorator rozwiązań.

|Nazwa pliku|Opis|
|---------------|-----------------|
|*Projname*. h|Główny plik dołączania zawierający definicje interfejsu C++ i deklaracje GUID elementów zdefiniowanych w ATLSample. idl. Jest on ponownie generowany przez MIDL podczas kompilacji.|
|*Projname*. cpp|Główny plik źródłowy programu. Zawiera implementację eksportu biblioteki DLL dla serwera w procesie i implementacji `WinMain` dla serwera lokalnego. W przypadku usługi to dodatkowo implementuje wszystkie funkcje zarządzania usługą.|
|Resource.h|Plik nagłówkowy pliku zasobów.|
|StdAfx. cpp|Obejmuje pliki StdAfx. h i atlimpl. cpp.|
|StdAfx. h|Zawiera pliki nagłówkowe ATL.|

## <a name="see-also"></a>Zobacz też

[Typy plików utworzone dla projektów Visual Studio C++](file-types-created-for-visual-cpp-projects.md)<br>
[Program MFC lub źródło kontroli i pliki nagłówkowe](mfc-program-or-control-source-and-header-files.md)<br>
[Projekty CLR](files-created-for-clr-projects.md)
