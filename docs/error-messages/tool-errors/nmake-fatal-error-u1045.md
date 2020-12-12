---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1045'
title: Błąd krytyczny NMAKE U1045
ms.date: 08/11/2019
f1_keywords:
- U1045
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
ms.openlocfilehash: 722525d917b7511dfe2294adf2e796efd3078913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322898"
---
# <a name="nmake-fatal-error-u1045"></a>Błąd krytyczny NMAKE U1045

> Niepowodzenie duplikowania: *komunikat*

Program lub polecenie wywoływane przez NMAKE nie powiodło się z powodu przyczyny w *komunikacie*. Gdy NMAKE wywołuje inny program, na przykład kompilator lub konsolidator, wywołanie może zakończyć się niepowodzeniem. Lub błąd może zostać zwrócony przez wywołany program. Ten komunikat służy do zgłaszania błędu.

Aby rozwiązać ten problem, należy najpierw określić przyczynę błędu. Możesz użyć poleceń zgłoszonych przez opcję NMAKE [/n](../../build/reference/running-nmake.md#nmake-options) , aby sprawdzić ustawienia środowiska i powtórzyć akcje wykonywane przez NMAKE w wierszu polecenia.
