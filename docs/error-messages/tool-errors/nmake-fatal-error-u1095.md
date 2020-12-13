---
description: 'Dowiedz się więcej na temat: błąd krytyczny NMAKE U1095'
title: Błąd krytyczny NMAKE U1095
ms.date: 11/04/2016
f1_keywords:
- U1095
helpviewer_keywords:
- U1095
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
ms.openlocfilehash: 047c4aaca15917b884a44bd1e3e156bf8825274f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345345"
---
# <a name="nmake-fatal-error-u1095"></a>Błąd krytyczny NMAKE U1095

rozwinięty wiersz polecenia "CommandLine" jest zbyt długi

Po rozwinięciu makra dany wiersz polecenia przekracza limit długości wierszy poleceń dla systemu operacyjnego.

System MS-DOS dopuszcza do 128 znaków w wierszu polecenia.

Jeśli polecenie dotyczy programu, który może akceptować dane wejściowe wiersza polecenia z pliku, należy zmienić polecenie i podać dane wejściowe z pliku na dysku lub w pliku wbudowanym. Na przykład LINK i LIB akceptują dane wejściowe z pliku odpowiedzi.
