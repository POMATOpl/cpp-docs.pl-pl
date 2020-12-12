---
description: 'Dowiedz się więcej o: błąd kompilatora C2170'
title: Błąd kompilatora C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 2f6093221d214aa12f6b90f40dde14518e44e08e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322261"
---
# <a name="compiler-error-c2170"></a>Błąd kompilatora C2170

"Identyfikator": nie zadeklarowano jako funkcja, nie może być wewnętrzna

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Pragma `intrinsic` jest używana dla elementu innego niż funkcja.

1. Pragma `intrinsic` jest używana w przypadku funkcji bez formy wewnętrznej.
