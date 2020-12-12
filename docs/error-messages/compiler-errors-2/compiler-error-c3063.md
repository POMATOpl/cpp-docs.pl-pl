---
description: 'Dowiedz się więcej o: błąd kompilatora C3063'
title: Błąd kompilatora C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: 304359e34b6cbae07d2f901db02c6e5ed04e373c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281707"
---
# <a name="compiler-error-c3063"></a>Błąd kompilatora C3063

operator "operator": wszystkie operandy muszą mieć ten sam typ wyliczeniowy

W przypadku używania operatorów w modułach wyliczających oba operandy muszą być typu wyliczeniowego. Aby uzyskać więcej informacji, zobacz [How to: define enums in C++/CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3063 i pokazuje, jak to naprawić:

```cpp
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```
