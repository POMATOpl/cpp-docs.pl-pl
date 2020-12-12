---
description: 'Dowiedz się więcej o: Porównywanie znaków'
title: Porównywanie znaków
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 0e00e087074a70145f1a73694293edc3c522d69f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297008"
---
# <a name="character-comparison"></a>Porównywanie znaków

Skorzystaj z następujących wskazówek:

- Porównywanie znanego bajtu wiodącego ze znakiem ASCII działa prawidłowo:

    ```cpp
    if( *sz1 == 'A' )
    ```

- Porównanie dwóch nieznanych znaków wymaga użycia jednego z makr zdefiniowanych w mbstring. h:

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   Gwarantuje to, że oba bajty znaku dwubajtowego są porównywane pod kątem równości.

## <a name="see-also"></a>Zobacz też

[Wskazówki dotyczące programowania MBCS](../text/mbcs-programming-tips.md)<br/>
[Przepełnienie buforu](../text/buffer-overflow.md)
