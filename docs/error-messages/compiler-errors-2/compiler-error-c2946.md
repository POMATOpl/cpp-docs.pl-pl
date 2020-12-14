---
description: 'Dowiedz się więcej o: błąd kompilatora C2946'
title: Błąd kompilatora C2946
ms.date: 11/04/2016
f1_keywords:
- C2946
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
ms.openlocfilehash: 7a74b17c10acd55a254c0d7fba5c8269689e3094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249506"
---
# <a name="compiler-error-c2946"></a>Błąd kompilatora C2946

jawne utworzenie wystąpienia; Klasa nie jest specjalizacją klasy szablonu

Nie można jawnie utworzyć wystąpienia klasy nieszablonowej.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2946.

```cpp
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```
