---
description: 'Dowiedz się więcej o: błąd kompilatora C2439'
title: Błąd kompilatora C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: 6493fb634581646c20a8d856658fe728ae27364c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189811"
---
# <a name="compiler-error-c2439"></a>Błąd kompilatora C2439

"Identyfikator": nie można zainicjować elementu członkowskiego

Nie można zainicjować klasy, struktury lub składowej Unii.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Podjęto próbę zainicjowania pośredniej klasy bazowej lub struktury.

1. Próba zainicjowania dziedziczonego elementu członkowskiego klasy lub struktury. Dziedziczony element członkowski musi być zainicjowany przez konstruktora klasy lub struktury.
