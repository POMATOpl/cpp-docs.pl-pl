---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2008'
title: Błąd narzędzi konsolidatora LNK2008
ms.date: 11/04/2016
f1_keywords:
- LNK2008
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
ms.openlocfilehash: 1897756ec6d46734604f243f617d9ce5a6bc375e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338489"
---
# <a name="linker-tools-error-lnk2008"></a>Błąd narzędzi konsolidatora LNK2008

Cel naprawy nie jest wyrównany "symbol_name"

LINK znalazł miejsce docelowe naprawy w pliku obiektu, które nie zostało prawidłowo wyrównane.

Przyczyną tego błędu może być niestandardowe wyrównanie secton (na przykład [pack](../../preprocessor/pack.md)#pragma), [wyrównanie](../../cpp/align-cpp.md) modyfikatora lub użycie kodu języka asemblera modyfikującego secton wyrównania.

Jeśli kod nie używa żadnego z powyższych, może to być spowodowane kompilatorem.
