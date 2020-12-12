---
description: 'Dowiedz się więcej na temat: błąd kompilatora zasobów zasobów RC2001'
title: Błąd kompilatora zasobów RC2001
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: 101ebb260bcfd24fb74368ca66e1e9d318418367
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206347"
---
# <a name="resource-compiler-error-rc2001"></a>Błąd kompilatora zasobów RC2001

stała nowego wiersza

Stała ciągu była kontynuowana w drugim wierszu bez ukośnika odwrotnego ( **\\** ) lub zamykania i otwierania podwójnych cudzysłowów (**"**).

Aby przerwać stałą ciągu, która znajduje się w dwóch wierszach w pliku źródłowym, wykonaj jedną z następujących czynności:

- Zakończ pierwszy wiersz za pomocą znaku kontynuacji wiersza, ukośnika odwrotnego.

- Zamknij ciąg w pierwszym wierszu ze znakiem podwójnego cudzysłowu i Otwórz ciąg w następnym wierszu z innym znakiem cudzysłowu.

Nie wystarczy, aby zakończyć pierwszy wiersz za pomocą \n, sekwencji unikowej osadzania znaku nowego wiersza w stałej ciągu.
