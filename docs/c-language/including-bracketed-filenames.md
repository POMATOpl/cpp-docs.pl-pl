---
description: 'Dowiedz się więcej na temat: w tym nazwy plików w nawiasach klamrowych'
title: Łącznie z nazwami plików w nawiasach
ms.date: 11/04/2016
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
ms.openlocfilehash: e54792b5feb7d5419896641c25a4367e97d80977
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182050"
---
# <a name="including-bracketed-filenames"></a>Łącznie z nazwami plików w nawiasach

**3.8.2 ANSI** Metoda lokalizowania plików źródłowych zawarcia

W przypadku specyfikacji plików ujętych w nawiasy ostre preprocesor nie przeszukuje katalogów plików nadrzędnych. Plik "nadrzędny" jest plikiem, który zawiera dyrektywę [#include](../preprocessor/hash-include-directive-c-cpp.md) . Zamiast tego rozpoczyna się od wyszukania pliku w katalogach określonych w wierszu polecenia kompilatora po/I. Jeśli/I opcja nie jest obecna lub kończy się niepowodzeniem, preprocesor używa zmiennej środowiskowej INCLUDE do znajdowania dowolnych plików dołączanych w nawiasach kątowych. Zmienna środowiskowa INCLUDE może zawierać wiele ścieżek oddzielonych średnikami (**;**). Jeśli więcej niż jeden katalog jest wyświetlany jako część opcji/I lub w zmiennej środowiskowej INCLUDE, preprocesor przeszukuje je w kolejności, w jakiej są wyświetlane.

## <a name="see-also"></a>Zobacz też

[Dyrektywy przetwarzania wstępnego](../c-language/preprocessing-directives.md)
