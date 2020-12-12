---
description: 'Dowiedz się więcej o: modyfikowalne elementy członkowskie danych (C++)'
title: Modyfikowalne elementy członkowskie danych (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: a288b382b456fa313c49832bd2d13aaceb269be9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313817"
---
# <a name="mutable-data-members-c"></a>Modyfikowalne elementy członkowskie danych (C++)

To słowo kluczowe może być stosowane tylko do niestatycznych i niestałych elementów członkowskich danych klasy. Jeśli element członkowski danych jest zadeklarowany **`mutable`** , dozwolone jest przypisanie wartości do tego elementu członkowskiego danych z **`const`** funkcji składowej.

## <a name="syntax"></a>Składnia

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Uwagi

Na przykład poniższy kod zostanie skompilowany bez błędu, ponieważ został `m_accessCount` zadeklarowany jako **`mutable`** , i w związku z tym może być modyfikowany przez `GetFlag` nawet wtedy, gdy `GetFlag` jest to stała funkcja członkowska.

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>Zobacz też

[Słowa kluczowe](../cpp/keywords-cpp.md)
