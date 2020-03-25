---
title: Ostrzeżenie kompilatora (poziom 1) C4376
ms.date: 11/04/2016
f1_keywords:
- C4376
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
ms.openlocfilehash: 8009d2e5d09ad173f6150ebe9a907be9f4947cd7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162859"
---
# <a name="compiler-warning-level-1-c4376"></a>Ostrzeżenie kompilatora (poziom 1) C4376

specyfikator dostępu "old_specifier:" nie jest już obsługiwany: Użyj zamiast tego "new_specifier:"

Aby uzyskać więcej informacji na temat określania dostępności typu i elementu członkowskiego w metadanych, zobacz [widoczność typów](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) i [widoczność elementów członkowskich](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) w artykule [jak definiować klasy i strukturyC++(/CLI) oraz korzystać](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)z nich.

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
