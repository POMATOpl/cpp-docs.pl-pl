---
description: 'Dowiedz się więcej na temat: Sprawdzanie nadpisywania pamięci'
title: Sprawdzanie nadpisywania pamięci
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 53361a6aea3de54017be3c966f9500accd21ced1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163174"
---
# <a name="checking-for-memory-overwrites"></a>Sprawdzanie nadpisywania pamięci

W przypadku naruszenia zasad dostępu w wywołaniu funkcji operowania sterty istnieje możliwość, że program spowodował uszkodzenie sterty. Typowym objawem takiej sytuacji jest:

```
Access Violation in _searchseg
```

Funkcja [_heapchk](../c-runtime-library/reference/heapchk.md) jest dostępna zarówno w kompilacjach debugowania, jak i wydań (tylko system Windows NT) na potrzeby weryfikowania integralności sterty biblioteki czasu wykonywania. Można użyć `_heapchk` w ten sam sposób, co `AfxCheckMemory` Funkcja do izolowania zastępowania sterty, na przykład:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Jeśli ta funkcja kiedykolwiek się nie powiedzie, należy wyizolować, w którym momencie sterta została uszkodzona.

## <a name="see-also"></a>Zobacz też

[Rozwiązywanie problemów z kompilacją wersji](fixing-release-build-problems.md)
