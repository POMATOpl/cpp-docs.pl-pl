---
description: Dowiedz się więcej na temat:/BIND
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: 87ea0265555991fca019760feec4395692c074ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187146"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>Uwagi

Ta opcja ustawia adresy punktów wejścia w tabeli adresów importu dla pliku wykonywalnego lub biblioteki DLL. Użyj tej opcji, aby skrócić czas ładowania programu.

Określ plik wykonywalny i biblioteki DLL programu w argumencie *Files* w wierszu polecenia polecenia EDITBIN. Opcjonalny argument *Path* /bind określa lokalizację bibliotek DLL używanych przez określone pliki. Oddziel wiele katalogów średnikami (**;**). Jeśli *ścieżka* nie zostanie określona, polecenia EDITBIN Przeszukuje katalogi określone w zmiennej środowiskowej PATH. Jeśli *ścieżka* jest określona, polecenia EDITBIN ignoruje zmienną PATH.

Domyślnie moduł ładujący programu ustawia adresy punktów wejścia podczas ładowania programu. Czas działania tego procesu zależy od liczby bibliotek DLL i liczby punktów wejścia, do których odwołuje się program. Jeśli program został zmodyfikowany z/BIND i jeśli adresy podstawowe dla pliku wykonywalnego i jego bibliotek DLL nie powodują konfliktu z bibliotek DLL, które są już załadowane, system operacyjny nie musi ustawiać tych adresów. W sytuacji, w której pliki są nieprawidłowo oparte, system operacyjny lokalizuje biblioteki DLL programu i ponownie oblicza adresy punktu wejścia, które dodaje do czasu ładowania programu.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)
