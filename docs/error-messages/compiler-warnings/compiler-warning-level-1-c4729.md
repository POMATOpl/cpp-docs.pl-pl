---
title: Kompilator ostrzeżenie (poziom 1) C4729
ms.date: 11/04/2016
f1_keywords:
- C4729
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
ms.openlocfilehash: f5f93cadd97eefe0d6c6da97be99ec5fd82ece24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386398"
---
# <a name="compiler-warning-level-1-c4729"></a>Kompilator ostrzeżenie (poziom 1) C4729

Funkcja za duża dla grafu przepływu na podstawie ostrzeżenia

To ostrzeżenie jest generowane, gdy funkcja jest zbyt duży, aby być skompilowana przy użyciu niezawodnych sprawdzanie w sytuacjach, generujących ostrzeżenia. To ostrzeżenie jest tylko wygenerowany, gdy [/Od](../../build/reference/od-disable-debug.md) — opcja kompilatora używane.

Aby rozwiązać tego ostrzeżenia, Podziel funkcji na mniejsze.