---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1852'
title: Błąd krytyczny C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 0b4976566b8101ecd4f35d20854ef6124a15246e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276247"
---
# <a name="fatal-error-c1852"></a>Błąd krytyczny C1852

"filename" nie jest prawidłowym prekompilowanym plikiem nagłówkowym

Plik nie jest prekompilowanym nagłówkiem.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Określono nieprawidłowy plik z **/Yu** lub **#pragma hdrstop**.

1. Kompilator zakłada rozszerzenie pliku. PCH, jeśli nie określisz inaczej.
