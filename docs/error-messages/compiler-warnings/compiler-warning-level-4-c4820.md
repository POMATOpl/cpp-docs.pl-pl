---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4820'
title: Ostrzeżenie kompilatora (poziom 4) C4820
ms.date: 11/04/2016
f1_keywords:
- C4820
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
ms.openlocfilehash: 778bf605d6ee1441e9efd68380c64d231df03b69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330479"
---
# <a name="compiler-warning-level-4-c4820"></a>Ostrzeżenie kompilatora (poziom 4) C4820

'bajty' dopełnienie bajtami dodane po konstrukcji 'member_name'

Typ i kolejność elementów spowodowały, że kompilator dodaje uzupełnienie do końca struktury. Aby uzyskać więcej informacji na temat dopełnienia w strukturze, zobacz [align](../../cpp/align-cpp.md) .

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4820:

```cpp
// C4820.cpp
// compile with: /W4 /c
#pragma warning(default : 4820)

// Delete the following 4 lines to resolve.
__declspec(align(2)) struct MyStruct {
   char a;
   int i;   // C4820
};

// OK
#pragma pack(1)
__declspec(align(1)) struct MyStruct2 {
   char a;
   int i;
};
```
