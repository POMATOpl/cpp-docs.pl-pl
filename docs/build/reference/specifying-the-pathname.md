---
description: 'Dowiedz się więcej na temat: Określanie nazwy ścieżki'
title: Określanie nazwy ścieżki
ms.date: 11/04/2016
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
ms.openlocfilehash: a8c55822bcb19864955ffa37ef2dd4cb18765ae5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224533"
---
# <a name="specifying-the-pathname"></a>Określanie nazwy ścieżki

Każda opcja pliku wyjściowego akceptuje argument *nazwy ścieżki* , który może określać lokalizację i nazwę pliku wyjściowego. Argument może zawierać nazwę dysku, katalog i nazwę pliku. Między opcją i argumentem nie jest dozwolone żadne miejsce.

Jeśli nazwa *ścieżki* zawiera nazwę pliku bez rozszerzenia, kompilator nadaje dane wyjściowe domyślne rozszerzenie. Jeśli nazwa *ścieżki* zawiera katalog, ale nie ma nazwy pliku, kompilator tworzy plik o nazwie domyślnej w określonym katalogu. Nazwa domyślna jest oparta na podstawowej nazwie pliku źródłowego i domyślnym rozszerzeniu na podstawie typu pliku wyjściowego. W przypadku pozostawienia całkowicie wyłączonej *nazwy ścieżki* kompilator tworzy plik o nazwie domyślnej w katalogu domyślnym.

Alternatywnie *argument nazwy* może być nazwą urządzenia (AUX, con, PRN lub NUL), a nie nazwą pliku. Nie należy używać spacji między opcją a nazwą urządzenia lub dwukropek jako częścią nazwy urządzenia.

|Nazwa urządzenia|Reprezentuje|
|-----------------|----------------|
|POMOCNICZ|Urządzenie pomocnicze|
|CON|Konsola|
|PRN|Drukarka|
|NUL|Urządzenie o wartości null (nie utworzono pliku)|

## <a name="example"></a>Przykład

Następujący wiersz polecenia wysyła mapfile do drukarki:

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
