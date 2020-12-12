---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1056'
title: Błąd krytyczny NMAKE U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: beb7814d2e29665e1f92c7ef1e8dadbd66af5d63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330382"
---
# <a name="nmake-fatal-error-u1056"></a>Błąd krytyczny NMAKE U1056

nie można znaleźć procesora poleceń

Procesor poleceń nie znajduje się w ścieżce określonej w zmiennych środowiskowych **wywołana** lub **Path** .

NMAKE używa COMMAND.COM lub CMD.EXE jako procesora poleceń podczas wykonywania poleceń. Szuka najpierw procesora poleceń w ścieżce ustawionej w **wywołana**. Jeśli **wywołana** nie istnieje, NMAKE Przeszukuje katalogi określone w polu **ścieżka**.
