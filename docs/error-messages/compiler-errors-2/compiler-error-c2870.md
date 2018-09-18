---
title: Błąd kompilatora C2870 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47101cbc2fb1be48ba54166b9c6ef99fc0c6c35e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073879"
---
# <a name="compiler-error-c2870"></a>Błąd kompilatora C2870

"name": definicja przestrzeni nazw musi znajdować się w zakresie pliku albo natychmiast w innej definicji przestrzeni nazw

Definicja przestrzeni nazw `name` niepoprawnie. Przestrzenie nazw musi być zdefiniowany w zakresie pliku (na zewnątrz wszystkich bloków i klasy) lub bezpośrednio w innej przestrzeni nazw.

Poniższy przykład spowoduje wygenerowanie C2870:

```
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```