---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4616'
title: Ostrzeżenie kompilatora (poziom 1) C4616
ms.date: 11/04/2016
f1_keywords:
- C4616
helpviewer_keywords:
- C4616
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
ms.openlocfilehash: 55ddc805c12cdc33947ca1f76c744610a5650497
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208700"
---
# <a name="compiler-warning-level-1-c4616"></a>Ostrzeżenie kompilatora (poziom 1) C4616

\#Ostrzeżenie pragma: ostrzeżenie numer "number" nie jest prawidłowym ostrzeżeniem kompilatora

Nie można ponownie przypisać numeru ostrzegawczego określonego w pragmie [ostrzeżenia](../../preprocessor/warning.md) . Pragma została zignorowana.

Poniższy przykład generuje C4616:

```cpp
// C4616.cpp
// compile with: /W1 /c
#pragma warning( disable : 0 )   // C4616
#pragma warning( disable : 999 )   // OK
#pragma warning( disable : 4998 )   // OK
```
