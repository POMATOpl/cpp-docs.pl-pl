---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1245'
title: Błąd narzędzi konsolidatora LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 3903651992f8fb79c3a79e4f2afc9d84e70e8126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193906"
---
# <a name="linker-tools-error-lnk1245"></a>Błąd narzędzi konsolidatora LNK1245

określono nieprawidłowy podsystem "Subsystem"; /SUBSYSTEM musi być WINDOWS, WINDOWSCE lub KONSOLą

do skompilowania obiektu użyto [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) , a jeden z następujących warunków został spełniony:

- Zdefiniowano niestandardowy punkt wejścia ([/entry](../../build/reference/entry-entry-point-symbol.md)), który nie może wywnioskować podsystemu przez konsolidator.

- Wartość została przeniesiona do opcji konsolidatora [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) , która nie jest prawidłowa dla obiektów/CLR.

W obu przypadkach rozdzielczość jest określona dla opcji konsolidatora/SUBSYSTEM.
