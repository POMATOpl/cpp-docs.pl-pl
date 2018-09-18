---
title: Kompilator ostrzeżenie (poziom 1) C4042 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bef2071cf31123b5b172df2651c0d6a6d87d4fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067479"
---
# <a name="compiler-warning-level-1-c4042"></a>Kompilator ostrzeżenie (poziom 1) C4042

'Identyfikator': ma złą klasę magazynu

Klasa wybrany magazyn nie można używać z tego identyfikatora w tym kontekście. Kompilator używa domyślnej klasy magazynu, zamiast tego:

- `extern`, jeśli *identyfikator* jest funkcją.

- **automatyczne**, jeśli *identyfikator* formalny parametr lub zmienna lokalna.

- Brak magazynu klasy, jeśli *identyfikator* jest zmienną globalną.

To ostrzeżenie może być spowodowany przez określenie klasę magazynu innego niż **zarejestrować** w deklaracji parametru.

Poniższy przykład spowoduje wygenerowanie C4042

```
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```