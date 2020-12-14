---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4580'
title: Ostrzeżenie kompilatora (poziom 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: 0bda682526081023c9208d548023f7c8b7316db9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294720"
---
# <a name="compiler-warning-level-3-c4580"></a>Ostrzeżenie kompilatora (poziom 3) C4580

[Attribute] jest przestarzały; Zamiast tego należy określić system:: Attribute lub platform:: Metadata jako klasę bazową

[[Attribute](../../windows/attributes/attribute.md)] nie jest już preferowaną składnią dla tworzenia atrybutów zdefiniowanych przez użytkownika. Aby uzyskać więcej informacji, zobacz [atrybuty zdefiniowane przez użytkownika](../../extensions/user-defined-attributes-cpp-component-extensions.md). W przypadku kodu CLR atrybuty pochodne od `System::Attribute` . Dla kodu środowisko wykonawcze systemu Windows atrybuty pochodne od `Platform::Metadata` .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3454 i pokazuje, jak rozwiązać ten problem.

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```
