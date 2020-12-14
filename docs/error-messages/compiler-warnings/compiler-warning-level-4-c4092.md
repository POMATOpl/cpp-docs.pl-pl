---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4092'
title: Ostrzeżenie kompilatora (poziom 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: 70b2d94304863610ede64a30bcb1bb6d407f2e12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262014"
---
# <a name="compiler-warning-level-4-c4092"></a>Ostrzeżenie kompilatora (poziom 4) C4092

> sizeof Zwraca "unsigned long"

Operand **`sizeof`** operatora był bardzo duży, dlatego został **`sizeof`** zwrócony **`unsigned long`** . To ostrzeżenie jest wykonywane w ramach rozszerzeń Microsoft ( [`/Ze`](../../build/reference/za-ze-disable-language-extensions.md) ). W obszarze zgodność ze standardem ANSI ( **`/Za`** ) wynik zostanie obcięty.
