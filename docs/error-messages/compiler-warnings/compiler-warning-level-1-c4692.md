---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4692'
title: Ostrzeżenie kompilatora (poziom 1) C4692
ms.date: 11/04/2016
f1_keywords:
- C4692
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
ms.openlocfilehash: 7c38a2bd4bfd4de943f64483cd8a9e96ece0b580
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249129"
---
# <a name="compiler-warning-level-1-c4692"></a>Ostrzeżenie kompilatora (poziom 1) C4692

'funkcja': podpis z nieprywatnego elementu członkowskiego zawiera typ macierzysty 'native_type' zestawu prywatnego

Typ widoczny poza zestawem zawiera funkcję członkowską, której podpis zawiera typ natywny, który nie jest widoczny poza zestawem. W związku z tym, funkcja członkowska nie powinna być wywoływana, jeśli jej typ zawierający jest skonkretyzowany poza zestawem.

Aby uzyskać więcej informacji, zobacz [typu widoczność](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji, zobacz [ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4692.

```cpp
// C4692.cpp
// compile with: /W1 /c /clr
#pragma warning(default:4692)
class Private_Native_Class {};
public class Public_Native_Class {};
public ref class Public_Ref_Class {
public:
   void Test(Private_Native_Class *) {}   // C4692
   void Test2(Public_Native_Class *) {}   // OK
};
```
