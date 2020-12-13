---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1071'
title: Błąd krytyczny C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: c4a6734dcb515b6d495eac720f83ba39be3c3677
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344383"
---
# <a name="fatal-error-c1071"></a>Błąd krytyczny C1071

znaleziono nieoczekiwany koniec pliku w komentarzu

Kompilator osiągnął koniec pliku podczas skanowania komentarza.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Brak terminatora komentarza (*/).

1. Brak znaku nowego wiersza po komentarzu w ostatnim wierszu pliku źródłowego.

Poniższy przykład generuje C1071:

```cpp
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```
