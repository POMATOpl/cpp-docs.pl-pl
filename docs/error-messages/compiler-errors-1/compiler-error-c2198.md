---
title: Błąd kompilatora C2198 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2198
dev_langs:
- C++
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a4e391f35a4487246ca074d218391348c83e0d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096824"
---
# <a name="compiler-error-c2198"></a>Błąd kompilatora C2198

'Funkcja': za mało argumentów dla wywołania

Kompilator odnaleziono za mało parametrów dla wywołania funkcji lub deklaracji Niepoprawna funkcja.

Poniższy przykład spowoduje wygenerowanie C2198:

```
// C2198.c
// compile with: /c
void func( int, int );
int main() {
   func( 1 );   // C2198 only one actual parameter
   func( 1, 1 );   // OK
}
```