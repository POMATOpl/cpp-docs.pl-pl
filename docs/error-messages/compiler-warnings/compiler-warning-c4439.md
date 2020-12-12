---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4439'
title: Ostrzeżenie kompilatora C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: 123f42ca495faeccc995dc1ac87572180d1dce70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180750"
---
# <a name="compiler-warning-c4439"></a>Ostrzeżenie kompilatora C4439

"Function": definicja funkcji z typem zarządzanym w podpisie musi mieć __clrcall konwencją wywoływania

Kompilator niejawnie zastąpił konwencją wywoływania z [`__clrcall`](../../cpp/clrcall.md) . Aby rozwiązać ten problem, Usuń **`__cdecl`** **`__stdcall`** konwencję wywoływania lub.

C4439 jest zawsze wystawiony jako błąd. Aby uzyskać więcej informacji, można wyłączyć to ostrzeżenie z `#pragma warning` lub **`/wd`** ; Zobacz [Ostrzeżenie](../../preprocessor/warning.md) lub [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/we,/wo,/WV,/WX (poziom ostrzeżenia)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4439.

```cpp
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```
