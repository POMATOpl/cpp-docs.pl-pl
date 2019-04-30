---
title: Kompilator ostrzeżenie (poziom 4) C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: c7c10273e06ec35528dbd9d51c02bb844d275638
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401257"
---
# <a name="compiler-warning-level-4-c4201"></a>Kompilator ostrzeżenie (poziom 4) C4201

użyto niestandardowego rozszerzenia: typ struct/union

W obszarze rozszerzenia Microsoft (/Ze) można określić strukturę bez deklarator jako elementy członkowskie innej struktury lub Unii. Te struktury wygenerowanie błędu w obszarze zgodności ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Przykład

```
// C4201.cpp
// compile with: /W4
struct S
{
   float y;
   struct
   {
      int a, b, c;  // C4201
   };
} *p_s;

int main()
{
}
```