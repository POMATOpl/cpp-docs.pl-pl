---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4324'
title: Ostrzeżenie kompilatora (poziom 4) C4324
ms.date: 11/04/2016
f1_keywords:
- C4324
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
ms.openlocfilehash: 96554085fa63f4a4f91b954c1f32960b19f1dc6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294551"
---
# <a name="compiler-warning-level-4-c4324"></a>Ostrzeżenie kompilatora (poziom 4) C4324

"struct_name": struktura została uzupełniona ze względu na __declspec (align ())

Dopełnienie zostało dodane na końcu struktury, ponieważ określono wartość [__declspec (align)](../../cpp/align-cpp.md) .

Na przykład poniższy kod generuje C4324:

```cpp
// C4324.cpp
// compile with: /W4
struct __declspec(align(32)) A
{
   char a;
};   // C4324

int main()
{
}
```
