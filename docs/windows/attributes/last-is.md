---
description: 'Dowiedz się więcej na temat: last_is'
title: last_is (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.last_is
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
ms.openlocfilehash: 41f436d1cd4317385d702d8763d69e6df7d07849
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327542"
---
# <a name="last_is"></a>last_is

Określa indeks ostatniego elementu tablicy, który ma zostać przesłany.

## <a name="syntax"></a>Składnia

```cpp
[ last_is("expression") ]
```

### <a name="parameters"></a>Parametry

*expression*<br/>
Co najmniej jedno wyrażenie języka C. Puste gniazda argumentów są dozwolone.

## <a name="remarks"></a>Uwagi

Atrybut **last_is** C++ ma takie same funkcje jak atrybut [last_is](/windows/win32/Midl/last-is) MIDL.

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
[length_is](length-is.md)<br/>
[size_is](size-is.md)
