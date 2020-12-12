---
description: 'Dowiedz się więcej na temat: przepełnienie buforu'
title: Przepełnienie buforu
ms.date: 11/04/2016
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
ms.openlocfilehash: 17da102b9a48a34d9879c08f0470ced3852ed0ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187601"
---
# <a name="buffer-overflow"></a>Przepełnienie buforu

Różne rozmiary znaków mogą spowodować problemy podczas umieszczania znaków w buforze. Rozważmy następujący kod, który kopiuje znaki z ciągu, `sz` w buforze `rgch` :

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
    rgch[ cb++ ] = *sz++;
```

Pytanie: czy ostatni bajt skopiował bajt wiodący? Poniższe rozwiązanie nie rozwiązuje problemu, ponieważ może spowodować przepełnienie buforu:

```cpp
cb = 0;
while( cb < sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

`_mbccpy`Wywołanie próbuje wykonać poprawną czynność — Skopiuj pełny znak, niezależnie od tego, czy jest to 1 czy 2 bajty. Ale nie przyjmuje się, że ostatni skopiowany znak może nie pasować do buforu, jeśli znak jest 2 b szerokości. Poprawne rozwiązanie to:

```cpp
cb = 0;
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )
{
    _mbccpy( rgch + cb, sz );
    cb += _mbclen( sz );
    sz = _mbsinc( sz );
}
```

Ten kod sprawdza możliwy przepełnienie buforu w teście pętli, przy użyciu `_mbclen` do testowania rozmiaru bieżącego znaku wskazywanego przez `sz` . Wykonując wywołanie `_mbsnbcpy` funkcji, można zamienić kod w **`while`** pętli na pojedynczy wiersz kodu. Na przykład:

```cpp
_mbsnbcpy( rgch, sz, sizeof( rgch ) );
```

## <a name="see-also"></a>Zobacz też

[Wskazówki dotyczące programowania MBCS](../text/mbcs-programming-tips.md)
