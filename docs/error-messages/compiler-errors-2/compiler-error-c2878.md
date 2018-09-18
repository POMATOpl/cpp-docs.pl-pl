---
title: Błąd kompilatora C2878 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2878
dev_langs:
- C++
helpviewer_keywords:
- C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4715d7eb83ffac3272f6187c6b67bae1af97ba64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021424"
---
# <a name="compiler-error-c2878"></a>Błąd kompilatora C2878

"name": przestrzeń nazw lub klasa o tej nazwie nie istnieje

Wprowadzone odwołanie do przestrzeni nazw lub klasy, która nie jest zdefiniowana.

Poniższy przykład spowoduje wygenerowanie C2878:

```
// C2878.cpp
// compile with: /c
namespace A {}
namespace B = C;   // C2878 namespace C doesn't exist
namespace B = A;
```