---
description: 'Dowiedz się więcej o: błąd kompilatora C2414'
title: Błąd kompilatora C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: 5bf2d017ac0018fe092b5a003dee021dd13370b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340336"
---
# <a name="compiler-error-c2414"></a>Błąd kompilatora C2414

niedozwolona liczba operandów

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Kod operacji nie obsługuje liczby użytych operandów. Zapoznaj się z instrukcją Skorowidz języka zestawu, aby określić poprawną liczbę operandów.

1. Nowszy procesor obsługuje instrukcję z inną liczbą operandów. Dostosuj opcję [/arch (minimalna architektura procesora)](../../build/reference/arch-minimum-cpu-architecture.md) , aby użyć późniejszego procesora.
