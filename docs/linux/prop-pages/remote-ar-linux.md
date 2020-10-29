---
title: Właściwości archiwum zdalnego (C++ Linux)
ms.date: 06/07/2019
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: 9e35c9cc0b8a99e87654f1052e8666c52e35a071
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924450"
---
# <a name="remote-archive-properties-c-linux"></a>Właściwości archiwum zdalnego (C++ Linux)

::: moniker range="msvc-140"

Obsługa systemu Linux jest dostępna w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range=">=msvc-150"

| Właściwość | Opis |
|--|--|
| Utwórz indeks Archiwum | Utwórz indeks archiwum (zgodnie z ranlib). Ta opcja umożliwia przyspieszenie konsolidacji i zmniejszenie zależności w ramach własnej biblioteki. |
| Utwórz cienkie Archiwum | Utwórz cienkie archiwum.  Cienkie archiwum zawierają ścieżki względne do obiektów zamiast osadzania obiektów.  Przełączenie między cienkim i normalnym wymaga usunięcia istniejącej biblioteki. |
| Brak ostrzeżenia podczas tworzenia | Nie ostrzega o tym, czy biblioteka została utworzona. |
| Obetnij sygnaturę czasową | Użyj wartości zero dla sygnatur czasowych i identyfikatorów UID/GIDs. |
| Pomiń transparent startowy | Nie pokazuj numeru wersji. |
| Pełny | Pełny |
| Opcje dodatkowe | Opcje dodatkowe. |
| Plik wyjściowy | Opcja/OUT zastępuje domyślną nazwę i lokalizację programu tworzonego przez bibliotekę. |
| Programu archiwizującego | Określa program do wywołania podczas łączenia obiektów statycznych lub ścieżkę do archiwum w systemie zdalnym. |
| Limit czasu Archiwum | Limit czasu zdalnego archiwum (w milisekundach). |
| Kopiuj dane wyjściowe | Określa, czy plik danych wyjściowych kompilacji ma być kopiowany z systemu zdalnego na maszynę lokalną. |

::: moniker-end
