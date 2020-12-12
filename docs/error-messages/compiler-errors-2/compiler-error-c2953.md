---
description: 'Dowiedz się więcej o: błąd kompilatora C2953'
title: Błąd kompilatora C2953
ms.date: 11/04/2016
f1_keywords:
- C2953
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
ms.openlocfilehash: 3bfc51d08318a4870f993a1d0cfe86eb1a38929e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210600"
---
# <a name="compiler-error-c2953"></a>Błąd kompilatora C2953

"Identyfikator": szablon klasy został już zdefiniowany

Sprawdź plik źródłowy i Uwzględnij pliki dla innych definicji.

Poniższy przykład generuje C2953:

```cpp
// C2953.cpp
// compile with: /c
template <class T>  class A {};
template <class T>  class A {};   // C2953
template <class T>  class B {};   // OK
```
