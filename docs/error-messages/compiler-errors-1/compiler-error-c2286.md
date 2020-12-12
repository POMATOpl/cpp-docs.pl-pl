---
description: 'Dowiedz się więcej o: błąd kompilatora C2286'
title: Błąd kompilatora C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 89c8b69c42188d448fad0cd08287773d7a713d08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298464"
---
# <a name="compiler-error-c2286"></a>Błąd kompilatora C2286

wskaźniki do składowych reprezentacji "identifier" są już ustawione na "dziedziczenie" — Deklaracja została zignorowana

Istnieją dwie różne reprezentacje wskaźników do elementów członkowskich dla klasy.

Aby uzyskać więcej informacji, zobacz [słowa kluczowe dziedziczenia](../../cpp/inheritance-keywords.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C2286:

```cpp
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
