---
title: Błąd krytyczny kompilatora zasobów RW1022 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1022
dev_langs:
- C++
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f57bb435d17cf1d539d558b5dead9c299f83494a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319185"
---
# <a name="resource-compiler-fatal-error-rw1022"></a>Błąd krytyczny kompilatora zasobów RW1022
**We/Wy błąd zapisu pliku**  
  
 Kompilator zasobów nie można zapisać do pliku.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać problem, sprawdzając następujące możliwe przyczyny  
  
1.  Za mało miejsca. Ilość wolnego miejsca musi wynosić co najmniej dwa razy rozmiar tworzonego pliku wykonywalnego.  
  
2.  Wolumin jest tylko do odczytu.  
  
3.  Uszkodzone sektory.  
  
4.  Nastąpiło naruszenie zasad współużytkowania.