---
title: Błąd kompilatora C3237 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3237
dev_langs:
- C++
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbfeb7775bc6d48078affcc37c2dead3c920307a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068614"
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