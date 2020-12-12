---
description: 'Dowiedz się więcej na temat: pliki wejściowe LIB'
title: Pliki wyjściowe LIB
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: f40cba91f0772e0073daca20a8f2093f3eec8aec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199548"
---
# <a name="lib-input-files"></a>Pliki wyjściowe LIB

Pliki wejściowe oczekiwane przez LIB są zależne od trybu, w którym jest używany, jak pokazano w poniższej tabeli.

|Tryb|Dane wejściowe|
|----------|-----------|
|Domyślne (Kompilowanie lub modyfikowanie biblioteki)|Pliki obiektów COFF (. obj), biblioteki COFF (. lib), 32-bitowe obiekty format (OMF) obiektu (. obj)|
|Wyodrębnianie elementu członkowskiego z elementem/EXTRACT|Biblioteka COFF (. lib)|
|Kompilowanie pliku eksportu i biblioteki importowanej za pomocą/DEF|Plik definicji modułu (. def), pliki obiektów COFF (. obj), biblioteki COFF (. lib), 32-bitowe pliki obiektów OMF (. obj)|

> [!NOTE]
> Bibliotek OMF utworzonych przez 16-bitową wersję biblioteki LIB nie można użyć jako danych wejściowych do 32-bitowej wersji biblioteki LIB.

## <a name="see-also"></a>Zobacz też

[Informacje o LIB](overview-of-lib.md)
