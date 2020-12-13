---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1099'
title: Błąd krytyczny NMAKE U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: 8044010cf967e4fe27b2235968022023d66ae1c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345319"
---
# <a name="nmake-fatal-error-u1099"></a>Błąd krytyczny NMAKE U1099

przepełnienie stosu

Przetwarzany plik reguł programu make był zbyt skomplikowany dla bieżącego przydziału stosu w NMAKE. NMAKE ma alokację 0x3000 (12K).

Aby zwiększyć alokację stosu NMAKE, uruchom narzędzie [polecenia EDITBIN/Stack](../../build/reference/stack.md) z większą opcją stosu:

**polecenia EDITBIN/STACK: rezerwacja NMAKE.EXE**

gdzie *rezerwa* jest liczbą większą niż bieżąca alokacja stosu w NMAKE.
