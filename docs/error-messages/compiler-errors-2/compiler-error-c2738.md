---
title: Błąd kompilatora C2738 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2738
dev_langs:
- C++
helpviewer_keywords:
- C2738
ms.assetid: 896b4640-1ee0-4cd8-9910-de3efa30006a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78dad09ba06e3f78007125508aa11de1a76101a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066624"
---
# <a name="compiler-error-c2738"></a>Błąd kompilatora C2738

"deklaracją": jest niejednoznaczny lub nie jest elementem członkowskim "type"

Funkcja została zadeklarowana niepoprawnie.

Poniższy przykład spowoduje wygenerowanie C2738:

```
// C2738.cpp
struct A {
   template <class T> operator T*();
   // template <class T> operator T();
};

template <>
A::operator int() {   // C2738

// try the following line instead
// A::operator int*() {

// or use the commented member declaration

   return 0;
}
```