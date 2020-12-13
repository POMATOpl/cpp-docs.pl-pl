---
description: 'Dowiedz się więcej na temat: dane wejściowe i wyjściowe'
title: Dane wejściowe i wyjściowe
ms.date: 11/04/2016
f1_keywords:
- c.io
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
ms.openlocfilehash: 0edd66765f1633dc0adf12b311faf81d3a030512
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334292"
---
# <a name="input-and-output"></a>Dane wejściowe i wyjściowe

Funkcje we/wy odczytują i zapisują dane do i z plików i urządzeń. Operacje we/wy na plikach odbywają się w trybie tekstowym lub w trybie binarnym. Biblioteka wykonawcza firmy Microsoft ma trzy typy funkcji we/wy:

- Funkcje [we/wy strumienia](../c-runtime-library/stream-i-o.md) traktują dane jako strumień pojedynczych znaków.

- Funkcje [we/wy niskiego poziomu](../c-runtime-library/low-level-i-o.md) wywołują system operacyjny bezpośrednio dla operacji niższego poziomu niż zapewniane przez we/wy strumienia.

- Funkcje [we/wy konsoli i portu](../c-runtime-library/console-and-port-i-o.md) odczytują lub zapisują bezpośrednio do konsoli (klawiatura i ekran) lub portu we/wy (na przykład portu drukarki).

   > [!NOTE]
   > Ponieważ funkcje strumienia są funkcjami buforowanymi i niskiego poziomu, te dwa typy funkcji są zwykle niezgodne. W przypadku przetwarzania określonego pliku Użyj wyłącznie funkcji Stream lub niskiego poziomu.

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
