---
title: Błąd kompilatora C2433 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2433
dev_langs:
- C++
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 081e63c83909319164a2903d8277a0b26a1e6901
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059956"
---
# <a name="compiler-error-c2433"></a>Błąd kompilatora C2433

'Identyfikator': 'modyfikator"nie jest dozwolone w deklaracjach danych

`friend`, `virtual`, I `inline` modyfikatorów nie można używać dla deklaracji danych.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2433.

```
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```