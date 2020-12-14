---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4057'
title: Ostrzeżenie kompilatora (poziom 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 0b5da5c4768f4101b7b1780b5d0518ed723c5225
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262090"
---
# <a name="compiler-warning-level-4-c4057"></a>Ostrzeżenie kompilatora (poziom 4) C4057

"operator": pośredni "Identifier1" powoduje nieznacznie różne typy podstawowe z "identifier2"

Dwa wyrażenia wskaźnika odwołują się do różnych typów podstawowych. Wyrażenia są używane bez konwersji.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Mieszanie typów podpisane i niepodpisane.

1. Mieszanie **`short`** i **`long`** typy.
