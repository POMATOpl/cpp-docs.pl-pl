---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4376'
title: Ostrzeżenie kompilatora (poziom 1) C4376
ms.date: 11/04/2016
f1_keywords:
- C4376
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
ms.openlocfilehash: 1b91538026ce564e03b2f472f9770d94b4bfc5ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311344"
---
# <a name="compiler-warning-level-1-c4376"></a>Ostrzeżenie kompilatora (poziom 1) C4376

specyfikator dostępu "old_specifier:" nie jest już obsługiwany: Użyj zamiast tego "new_specifier:"

Aby uzyskać więcej informacji na temat określania dostępności typu i elementu członkowskiego w metadanych, zobacz [widoczność typów](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) i [widoczność elementów członkowskich](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) w artykule [jak definiować klasy i struktury (C++/CLI) oraz korzystać](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)z nich.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4376.

```cpp
// C4376.cpp
// compile with: /clr /W1 /c
public ref class G {
public public:   // C4376
   void m2();
};

public ref class H {
public:   // OK
   void m2();
};
```
