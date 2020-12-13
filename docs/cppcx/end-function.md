---
description: 'Dowiedz się więcej na temat: End Function'
title: End — funkcja
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::end
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
ms.openlocfilehash: e29595e7eb403af85abdbfa18782adf1c33c308e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341974"
---
# <a name="end-function"></a>End — funkcja

Zwraca iterator, który wskazuje poza końcem kolekcji, do której uzyskuje dostęp określony parametr interfejsu.

## <a name="syntax"></a>Składnia

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    end(
        IVector<T>^ v       );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    end(
        IVectorView<T>^ v
       );
template <typename T>
    ::Platform::Collections::InputIterator<T>
    end(
        IIterable<T>^ i
       );
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Parametr typu szablonu.

*v*<br/>
Kolekcja \<T> obiektów Vector lub VectorView, \<T> do których uzyskuje dostęp za pomocą \<T> interfejsu IVector lub IVectorView \<T> .

*i*<br/>
Kolekcja środowisko wykonawcze systemu Windows obiektów, do których uzyskuje dostęp \<T> interfejs IIterable.

### <a name="return-value"></a>Wartość zwracana

Iterator, który wskazuje poza końcem kolekcji.

### <a name="remarks"></a>Uwagi

Pierwsze dwie funkcje szablonu zwracają Iteratory, a trzecia funkcja szablonu zwraca iterator danych wejściowych.

Obiekt [platform:: Collections:: VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) zwracany przez `end` jest iteratorem serwera proxy, który przechowuje elementy typu `VectorProxy<T>` . Jednak obiekt proxy jest prawie nigdy niewidoczny dla kodu użytkownika. Aby uzyskać więcej informacji, zobacz [kolekcje (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Wymagania

**Nagłówek:** Collection. h

**Przestrzeń nazw:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Zobacz też

[Windows:: Foundation:: Collections, przestrzeń nazw](../cppcx/windows-foundation-collections-namespace-c-cx.md)
