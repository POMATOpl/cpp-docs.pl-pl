---
description: 'Dowiedz się więcej o: błąd kompilatora C2415'
title: Błąd kompilatora C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: 21bbeabe0a5eacea55d2a38ab515429e6468ba57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340349"
---
# <a name="compiler-error-c2415"></a>Błąd kompilatora C2415

niewłaściwy typ operandu

Kod operacji nie używa operandów tego typu.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Kod operacji nie obsługuje liczby użytych operandów. Zapoznaj się z instrukcją Skorowidz języka zestawu, aby określić poprawną liczbę operandów.

1. Nowszy procesor obsługuje instrukcję z dodatkowymi typami. Dostosuj opcję [/arch (minimalna architektura procesora)](../../build/reference/arch-minimum-cpu-architecture.md) , aby użyć późniejszego procesora.
