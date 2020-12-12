---
description: 'Dowiedz się więcej o: błąd kompilatora C3839'
title: Błąd kompilatora C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: 8b34cdd7f09bea924d3e184f7ea639c3f8210ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180802"
---
# <a name="compiler-error-c3839"></a>Błąd kompilatora C3839

nie można zmienić wyrównania w typie zarządzanym lub WinRT

Wyrównanie zmiennych w typach zarządzanych lub środowisko wykonawcze systemu Windows jest kontrolowane przez środowisko CLR lub środowisko wykonawcze systemu Windows i nie można ich modyfikować przy użyciu funkcji [align](../../cpp/align-cpp.md).

Poniższy przykład generuje C3839:

```cpp
// C3839a.cpp
// compile with: /clr
ref class C
{
public:
   __declspec(align(32)) int m_j; // C3839
};

int main()
{
}
```
