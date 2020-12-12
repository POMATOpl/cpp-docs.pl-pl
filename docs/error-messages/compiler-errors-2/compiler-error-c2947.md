---
description: 'Dowiedz się więcej o: błąd kompilatora C2947'
title: Błąd kompilatora C2947
ms.date: 11/04/2016
f1_keywords:
- C2947
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
ms.openlocfilehash: 5b1780d49f97bfab33e70a4dd7b1958b56c8df14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189486"
---
# <a name="compiler-error-c2947"></a>Błąd kompilatora C2947

Oczekiwano elementu ">" do zakończenia konstruowania, znaleziono "SYNTAX"

Lista argumentów generycznych lub szablonów nie została prawidłowo zakończona.

C2947 mogą być również generowane przez błędy składniowe.

Poniższy przykład generuje C2947:

```cpp
// C2947.cpp
// compile with: /c
template <typename T>=   // C2947
// try the following line instead
// template <typename T>
struct A {};
```
