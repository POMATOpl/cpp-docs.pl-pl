---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4094'
title: Ostrzeżenie kompilatora (poziom 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: 63c554703c1eb6f7ecb831d1046641a0cde2094a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326534"
---
# <a name="compiler-warning-level-2-c4094"></a>Ostrzeżenie kompilatora (poziom 2) C4094

nieoznakowany "token" zadeklarowany jako brak symboli

Kompilator wykrył pustą deklarację przy użyciu nieoznakowanej struktury, Unii lub klasy. Deklaracja jest ignorowana.

## <a name="example"></a>Przykład

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Ten stan generuje błąd w obszarze zgodność ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)).
