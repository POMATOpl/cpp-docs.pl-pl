---
title: Ostrzeżenie LNK4010 narzędzi konsolidatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4010
dev_langs:
- C++
helpviewer_keywords:
- LNK4010
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 266e377a917fe3ce9ae7bae228134f49384e15cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4010"></a>Ostrzeżenie LNK4010 narzędzi konsolidatora
Nieprawidłowy numer wersji podsystemu numer; przyjęto domyślną wersję podsystemu  
  
 Można określić wersji podsystemu obrazu ([/Subsystem](../../build/reference/subsystem-specify-subsystem.md)). Każdego podsystemu ma wymagania dotyczące minimalnej wersji. Jeśli określona wersja jest niższa niż wartość minimalna, nastąpi to ostrzeżenie i konsolidator użyje tylko podsystemu domyślne.