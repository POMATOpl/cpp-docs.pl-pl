---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziomy 2 i 3) C4008'
title: Ostrzeżenie kompilatora (poziomy 2 i 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 6f13ef60efabeaffe549189431aa04c65a12cbe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234426"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Ostrzeżenie kompilatora (poziomy 2 i 3) C4008

"Identyfikator": atrybut "Attribute" został zignorowany

Kompilator zignorował **`__fastcall`** **`static`** atrybut,, lub **`inline`** dla funkcji (ostrzeżenie poziomu 3) lub dane (poziom 2 ostrzeżenie).

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. **`__fastcall`** atrybut z danymi.

1. **`static`** lub **`inline`** atrybut z funkcją **Main** .
