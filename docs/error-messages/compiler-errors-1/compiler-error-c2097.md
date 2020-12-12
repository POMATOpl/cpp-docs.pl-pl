---
description: 'Dowiedz się więcej o: błąd kompilatora C2097'
title: Błąd kompilatora C2097
ms.date: 11/04/2016
f1_keywords:
- C2097
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
ms.openlocfilehash: b9aa67f85ce9ba60a693500a2d7e3f69014cbba3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278613"
---
# <a name="compiler-error-c2097"></a>Błąd kompilatora C2097

niedozwolona Inicjalizacja

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Inicjalizacja zmiennej przy użyciu wartości niestałej.

1. Inicjalizacja krótkiego adresu o długim adresie.

1. Inicjacja struktury lokalnej, Unii lub tablicy z niestałym wyrażeniem podczas kompilowania z **/za**.

1. Inicjowanie z wyrażeniem zawierającym operator przecinkowy.

1. Inicjowanie przy użyciu wyrażenia, które nie jest stałe ani symboliczne.
