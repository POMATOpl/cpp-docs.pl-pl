---
description: 'Dowiedz się więcej o: funkcja BEGIN'
title: BEGIN — funkcja
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::begin
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
ms.openlocfilehash: ae59a4b4344da520d86c216f4c9979953e16753c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302767"
---
# <a name="begin-function"></a>BEGIN — funkcja

Zwraca iterator, który wskazuje na początek kolekcji, do której uzyskuje dostęp określony parametr interfejsu.

## <a name="syntax"></a>Składnia

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    begin(
          IVector<T>^ v         );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    begin(
          IVectorView<T>^ v
         );

template <typename T>
    ::Platform::Collections::InputIterator<T>
    begin(
          IIterable<T>^ i         );
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Parametr typu szablonu.

*v*<br/>
Kolekcja \<T> obiektów Vector lub VectorView \<T> , do których uzyskuje dostęp interfejs IVector \<T> lub IVectorView \<T> .

*i*<br/>
Kolekcja arbitralnych obiektów środowisko wykonawcze systemu Windows, do których uzyskuje dostęp \<T> interfejs IIterable.

### <a name="return-value"></a>Wartość zwracana

Iterator, który wskazuje na początek kolekcji.

### <a name="remarks"></a>Uwagi

Pierwsze dwie funkcje szablonu zwracają Iteratory, a trzecia funkcja szablonu zwraca iterator danych wejściowych.

Obiekt VectorIterator, który jest zwracany przez początek jest iteratorem serwera proxy, który przechowuje elementy typu VectorProxy \<T> . Jednak obiekt proxy jest prawie nigdy niewidoczny dla kodu użytkownika. Aby uzyskać więcej informacji, zobacz [kolekcje (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Wymagania

**Nagłówek:** Collection. h

**Przestrzeń nazw:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Zobacz też

[Windows:: Foundation:: Collections, przestrzeń nazw](../cppcx/windows-foundation-collections-namespace-c-cx.md)
