---
title: Kopiuj właściwości projektu źródła (Linux C++)
ms.date: 10/16/2019
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: 393f1b92bb5185bcd5ce93999e0c13f7d370e78d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924545"
---
# <a name="copy-sources-project-properties-linux-c"></a>Kopiuj właściwości projektu źródła (Linux C++)

::: moniker range="msvc-140"

Obsługa systemu Linux jest dostępna w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range=">=msvc-150"

Właściwości ustawione na tej stronie właściwości mają zastosowanie do wszystkich plików w projekcie, z wyjątkiem tego, których właściwości na poziomie plików są ustawione.

| Właściwość | Opis |
|--|--|
| Źródła do skopiowania | Określa źródła do skopiowania do systemu zdalnego. Zmiana tej listy może zmienić się lub w inny sposób mieć wpływ na strukturę katalogów, w której pliki są kopiowane do systemu zdalnego. |
| Kopiuj źródła | Określa, czy źródła mają być kopiowane do systemu zdalnego. |
| Dodatkowe źródła do skopiowania | Określa dodatkowe źródła do skopiowania do systemu zdalnego. Opcjonalnie możesz określić pary mapowania lokalnego do zdalnego przy użyciu składni podobnej do następującej: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2, gdzie plik lokalny można skopiować do określonej lokalizacji zdalnej w systemie zdalnym. |

@SourcesToCopyRemotely i @DataFilesToCopyRemotely zapoznaj się z grupami elementów w pliku projektu. Aby zmodyfikować źródła lub pliki danych, które są kopiowane zdalnie, edytuj plik *vcxproj* w następujący sposób:

```xml
<ItemGroup>
   <MyItems Include="foo.txt" />
   <MyItems Include="bar.txt" />
   <DataFilesToCopyRemotely Include="@(MyItems)" />
</ItemGroup>
```

::: moniker-end
