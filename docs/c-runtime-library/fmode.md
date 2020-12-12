---
description: 'Dowiedz się więcej na temat: _fmode'
title: _fmode
ms.date: 11/04/2016
f1_keywords:
- fmode
- _fmode
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
ms.openlocfilehash: c4e7932369a2ad63b5498078e46cd5610b679ee0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303902"
---
# <a name="_fmode"></a>_fmode

`_fmode`Zmienna ustawia domyślny tryb translacji plików dla tłumaczenia tekstowego lub binarnego. Ta zmienna globalna została uznana za przestarzałą dla bezpieczniejszych wersji funkcjonalnych [_get_fmode](../c-runtime-library/reference/get-fmode.md) i [_set_fmode](../c-runtime-library/reference/set-fmode.md), które powinny być używane zamiast zmiennej globalnej. Jest on zadeklarowany w STDLIB. h w następujący sposób.

## <a name="syntax"></a>Składnia

```
extern int _fmode;
```

## <a name="remarks"></a>Uwagi

Ustawieniem domyślnym `_fmode` jest `_O_TEXT` dla tłumaczenia w trybie tekstowym. `_O_BINARY` jest ustawieniem tryb binarny.

Można zmienić wartość `_fmode` na trzy sposoby:

- Połącz z Binmode. obj. Spowoduje to zmianę początkowego ustawienia `_fmode` na `_O_BINARY` , co spowoduje, że wszystkie pliki z wyjątkiem `stdin` , `stdout` i `stderr` mają być otwierane w trybie binarnym.

- Wykonaj wywołanie `_get_fmode` lub `_set_fmode` , aby odpowiednio uzyskać lub ustawić `_fmode` zmienną globalną.

- Zmień wartość `_fmode` bezpośrednio przez ustawienie jej w programie.

## <a name="see-also"></a>Zobacz też

[Zmienne globalne](../c-runtime-library/global-variables.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)
