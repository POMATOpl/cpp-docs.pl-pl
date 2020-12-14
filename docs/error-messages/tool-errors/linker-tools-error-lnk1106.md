---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1106'
title: Błąd narzędzi konsolidatora LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 85f353b6424cdd9ad12a99b29fec4f6119472cdb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281408"
---
# <a name="linker-tools-error-lnk1106"></a>Błąd narzędzi konsolidatora LNK1106

nieprawidłowy plik lub dysk: nie można przejść do lokalizacji

Narzędzie nie może odczytać lub zapisać `location` w pliku mapowanym do pamięci.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Dysk jest zapełniony.

   Zwolnij trochę miejsca i Połącz ponownie.

1. Próba połączenia przez sieć.

   Niektóre sieci nie obsługują w pełni plików mapowanych na pamięć używanych przez konsolidator. Spróbuj połączyć się na dysku lokalnym.

1. Zły blok na dysku.

   Mimo że sprzęt systemu operacyjnego i dysku powinien wykryć taki błąd, można uruchomić program do sprawdzania dysku.

1. Za mało miejsca na stercie.

   Aby uzyskać więcej informacji, zobacz [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) .
