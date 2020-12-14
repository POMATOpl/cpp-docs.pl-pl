---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1059'
title: Błąd krytyczny NMAKE U1059
ms.date: 08/27/2018
f1_keywords:
- U1059
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
ms.openlocfilehash: 025ea8577814519b883e534c54ed8cf4383ef029
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283540"
---
# <a name="nmake-fatal-error-u1059"></a>Błąd krytyczny NMAKE U1059

> Błąd składniowy: Brak znaku "}" w elemencie Dependent

Ścieżka wyszukiwania dla elementu zależnego została niepoprawnie określona. W ścieżce lub nawias zamykający (**}**) został pominięty.

Składnia specyfikacji katalogu dla elementu zależnego to

> **zależne od** **{** *katalogi* }

gdzie *katalogi* określa jedną lub więcej ścieżek, każda z nich oddzielona średnikiem (**;**). Spacje nie są dozwolone.

Jeśli część lub cała ścieżka wyszukiwania jest zastępowana przez makro, upewnij się, że nie ma żadnych spacji w rozwinięciu makra.
