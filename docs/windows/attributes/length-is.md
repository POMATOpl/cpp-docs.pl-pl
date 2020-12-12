---
description: 'Dowiedz się więcej na temat: length_is'
title: length_is (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: b3f913819b88958f294aee42f4cbda07827fa990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329845"
---
# <a name="length_is"></a>length_is

Określa liczbę elementów tablicy do przesłania.

## <a name="syntax"></a>Składnia

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>Parametry

*expression*<br/>
Co najmniej jedno wyrażenie języka C. Puste gniazda argumentów są dozwolone.

## <a name="remarks"></a>Uwagi

Atrybut **length_is** C++ ma takie same funkcje jak atrybut [length_is](/windows/win32/Midl/length-is) MIDL.

## <a name="example"></a>Przykład

Zobacz [first_is](first-is.md) , aby zapoznać się z przykładem, jak określić sekcję tablicy.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Pole w **`struct`** lub **`union`** , parametr interfejsu, metoda interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Atrybuty parametru](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[last_is](last-is.md)<br/>
[size_is](size-is.md)
