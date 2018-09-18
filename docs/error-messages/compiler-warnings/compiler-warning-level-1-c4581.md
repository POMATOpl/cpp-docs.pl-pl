---
title: Kompilator ostrzeżenie (poziom 1) C4581 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4581
dev_langs:
- C++
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 586283e41fb38baae828bf5a4380ec2afe323ecb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116051"
---
# <a name="compiler-warning-level-1-c4581"></a>Kompilator ostrzeżenie (poziom 1) C4581

zachowanie przestarzałe: "ciąg1" zastąpione "ciąg2", aby przetwarzać atrybut

Ten błąd można wygenerować w wyniku pracy zgodności kompilatora, która została wykonana dla programu Visual C++ 2005: Sprawdzanie parametrów dla atrybutów języka Visual C++.

W poprzednich wersjach wartości atrybutów zostały zaakceptowane, czy zostały one ujęta w znaki cudzysłowu. Jeśli wartość jest wyliczeniem, nie muszą być ujęte w znaki cudzysłowu.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C4581.

```
// C4581.cpp
// compile with: /c /W1
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {};

[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581
// try the following line instead
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]
class CSample : public IMyI {};
```