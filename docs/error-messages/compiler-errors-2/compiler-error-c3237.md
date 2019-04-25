---
title: Błąd kompilatora C3237
ms.date: 11/04/2016
f1_keywords:
- C3237
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
ms.openlocfilehash: 9853fd67c2b053e337cfacb5478e206c79321263
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173330"
---
# <a name="compiler-error-c3237"></a>Błąd kompilatora C3237

"generic_class": klasa generyczna nie może być atrybutem niestandardowym

Klasy ogólne nie może być atrybuty zdefiniowane przez użytkownika.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3237.

```
// C3237.cpp
// compile with: /clr /c
// C3237 expected
using namespace System;

generic <class T>
// Delete the following line to resolve.
[attribute(AttributeTargets::All, AllowMultiple=true)]
public ref class GR {};
```