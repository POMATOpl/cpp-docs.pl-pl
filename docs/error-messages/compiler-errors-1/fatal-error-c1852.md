---
title: Błąd krytyczny C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 540febabc8f2947f11b58cf7eadee53d47f7bef3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202881"
---
# <a name="fatal-error-c1852"></a>Błąd krytyczny C1852

"filename" nie jest prawidłowym prekompilowanym plikiem nagłówkowym

Plik nie jest prekompilowanym nagłówkiem.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Określono nieprawidłowy plik z **/Yu** lub **#pragma hdrstop**.

1. Kompilator zakłada rozszerzenie pliku. PCH, jeśli nie określisz inaczej.
