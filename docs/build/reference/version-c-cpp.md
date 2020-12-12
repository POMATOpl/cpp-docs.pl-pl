---
description: Dowiedz się więcej o wersji (C/C++)
title: WERSJA (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 1a63435c752220ab9fef54628ab101a14ef58582
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176395"
---
# <a name="version-cc"></a>WERSJA (C/C++)

Informuje LINK, aby umieścić numer w nagłówku pliku. exe lub DLL.

```
VERSION major[.minor]
```

## <a name="remarks"></a>Uwagi

Argumenty *Główne* i *pomocnicze* są liczbami dziesiętnymi z zakresu od 0 do 65 535. Wartość domyślna to 0,0.

Odpowiednikiem metody określania numeru wersji jest opcja [Informacje o wersji](version-version-information.md) (/Version).

## <a name="see-also"></a>Zobacz też

[Reguły dla instrukcji Module-Definition](rules-for-module-definition-statements.md)
