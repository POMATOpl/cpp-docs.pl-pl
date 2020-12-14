---
description: 'Dowiedz się więcej o: błąd kompilatora C2289'
title: Błąd kompilatora C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: ba9af908af6defaccd6825ce3dad412ad6914c77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185963"
---
# <a name="compiler-error-c2289"></a>Błąd kompilatora C2289

kwalifikator tego samego typu użyty więcej niż raz

Deklaracja typu lub definicja używa kwalifikatora typu ( **`const`** , **`volatile`** , **`signed`** lub **`unsigned`** ) więcej niż raz, co powoduje błąd pod kątem zgodności ze standardem ANSI (**/za**).

Poniższy przykład generuje C2286:

```cpp
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```
