---
description: 'Dowiedz się więcej o: znaki specjalne w makrach'
title: Znaki specjalne w makrach
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: 569aedbc474f660894b723f9356355e2360a4e61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224663"
---
# <a name="special-characters-in-macros"></a>Znaki specjalne w makrach

Znak numeru (#) po definicji określa komentarz. Aby określić znak numeru literału w makrze, użyj karetki (^), jak w ^ #.

Znak dolara ($) określa wywołanie makra. Aby określić literał $, należy użyć $ $.

Aby rozwinąć definicję do nowego wiersza, Zakończ wiersz z ukośnikiem odwrotnym ( \\ ). Po wywołaniu makra ukośnik odwrotny plus znak nowego wiersza jest zastępowany spacją. Aby określić literał odwróconej kreski ułamkowej na końcu wiersza, poprzedź go znakiem karetki (^) lub wykonaj za pomocą specyfikatora komentarza (#).

Aby określić literał znaku nowego wiersza, należy zakończyć wiersz znakiem karetki (^), jak w:

```
CMDS = cls^
dir
```

## <a name="see-also"></a>Zobacz też

[Definiowanie makra NMAKE](defining-an-nmake-macro.md)
