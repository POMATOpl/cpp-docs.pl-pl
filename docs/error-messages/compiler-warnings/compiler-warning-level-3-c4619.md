---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4619'
title: Ostrzeżenie kompilatora (poziom 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: c108e4d1a0845cc6629a36307c33fc8342cadd67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337263"
---
# <a name="compiler-warning-level-3-c4619"></a>Ostrzeżenie kompilatora (poziom 3) C4619

\#Ostrzeżenie pragma: nie istnieje ostrzeżenie o numerze "number"

Podjęto próbę wyłączenia ostrzeżenia, które nie istnieje.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4619:

```cpp
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```
