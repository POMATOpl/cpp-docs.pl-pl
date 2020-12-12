---
description: Dowiedz się więcej na temat dokumentacji XML (Visual C++)
title: Dokumentacja XML (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
ms.openlocfilehash: 762380d08483292866cb96b34be4d85f7a2f510a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260946"
---
# <a name="xml-documentation-visual-c"></a>Dokumentacja XML (Visual C++)

W Visual C++ można dodać komentarze do kodu źródłowego, który zostanie przetworzony do pliku. XML. Ten plik może następnie wejść do procesu, który tworzy dokumentację dla klas w kodzie.

W pliku z kodem Visual C++ komentarze dokumentacji XML muszą znajdować się bezpośrednio przed metodą lub definicją typu. Komentarze mogą służyć do wypełnienia etykietki danych sekcji szybkich informacji IntelliSense w następujących scenariuszach:

1. gdy kod jest kompilowany jako składnik środowisko wykonawcze systemu Windows z towarzyszącym plikiem. winmd

1. gdy kod źródłowy zostanie uwzględniony w bieżącym projekcie

1. w bibliotece, której deklaracje i implementacje typu znajdują się w tym samym pliku nagłówkowym

> [!NOTE]
> W bieżącej wersji Komentarze do kodu nie są przetwarzane w szablonach ani żadne elementy zawierające typ szablonu (na przykład funkcja pobierająca parametr jako szablon). Dodanie takich komentarzy spowoduje niezdefiniowane zachowanie.

Aby uzyskać szczegółowe informacje na temat tworzenia pliku XML z komentarzami dokumentacji, zobacz następujące tematy.

|Aby uzyskać informacje na temat|Zobacz|
|---------------------------|---------|
|Opcje kompilatora, które mają być używane|[/doc](doc-process-documentation-comments-c-cpp.md)|
|Tagi, których można użyć, aby zapewnić powszechnie używane funkcje w dokumentacji|[Zalecane Tagi dla komentarzy dokumentacji](recommended-tags-for-documentation-comments-visual-cpp.md)|
|Ciągi IDENTYFIKACYJNe generowane przez kompilator, aby identyfikować konstrukcje w kodzie|[Przetwarzanie pliku XML](dot-xml-file-processing.md)|
|Jak rozgraniczać Tagi dokumentacji|[Ograniczniki tagów dokumentacji Visual C++](delimiters-for-visual-cpp-documentation-tags.md)|
|Generowanie pliku XML z jednego lub więcej plików. xdc.|[Odwołanie XDCMake](xdcmake-reference.md)|
|Linki do informacji o formacie XML w odniesieniu do obszarów funkcji programu Visual Studio|[XML w programie Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)|

Jeśli konieczne jest umieszczenie znaków specjalnych XML w tekście komentarza do dokumentacji, należy użyć jednostek XML lub sekcji CDATA.

## <a name="see-also"></a>Zobacz też

[Component Extensions dla platform środowiska uruchomieniowego](../../extensions/component-extensions-for-runtime-platforms.md)
