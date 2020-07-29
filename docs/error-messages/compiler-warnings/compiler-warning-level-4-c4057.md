---
title: Ostrzeżenie kompilatora (poziom 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: d0bae91af3c2bfed97e252a74232e2a1bd778347
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225296"
---
# <a name="compiler-warning-level-4-c4057"></a>Ostrzeżenie kompilatora (poziom 4) C4057

"operator": pośredni "Identifier1" powoduje nieznacznie różne typy podstawowe z "identifier2"

Dwa wyrażenia wskaźnika odwołują się do różnych typów podstawowych. Wyrażenia są używane bez konwersji.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Mieszanie typów podpisane i niepodpisane.

1. Mieszanie **`short`** i **`long`** typy.
