---
description: 'Dowiedz się więcej na temat: jak używać gcnew do tworzenia typów wartości i używania niejawnego opakowania'
title: 'Porady: używanie funkcji gcnew do tworzenia typów wartości i korzystanie z niejawnej konwersji boxing'
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: e58b50be4399cef6a842ce0b02e951617f143e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210897"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>Porady: używanie funkcji gcnew do tworzenia typów wartości i korzystanie z niejawnej konwersji boxing

Użycie [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) w typie wartości spowoduje utworzenie opakowanego typu wartościowego, który można następnie umieścić na zarządzanej stercie ze stertą.

## <a name="example"></a>Przykład

```cpp
// vcmcppv2_explicit_boxing4.cpp
// compile with: /clr
public value class V {
public:
   int m_i;
   V(int i) : m_i(i) {}
};

public ref struct TC {
   void do_test(V^ v) {
      if (v != nullptr)
         ;
      else
         ;
   }
};

int main() {
   V^ v = gcnew V(42);
   TC^ tc = gcnew TC;
   tc->do_test(v);
}
```

## <a name="see-also"></a>Zobacz także

[Boxing](../extensions/boxing-cpp-component-extensions.md)
