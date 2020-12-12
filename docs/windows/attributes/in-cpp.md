---
description: 'Dowiedz się więcej na temat: w (C++)'
title: in (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: c4d19fcf7adc767986306a3ef55b26a2cc91dccf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321379"
---
# <a name="in-c"></a>in (C++)

Wskazuje, że parametr ma być przekazywać z procedury wywołującej do procedury wywoływanej.

## <a name="syntax"></a>Składnia

```cpp
[in]
```

## <a name="remarks"></a>Uwagi

Atrybut **in** języka C++ ma takie same funkcje jak atrybut [in](/windows/win32/Midl/in) MIDL.

## <a name="example"></a>Przykład

Zobacz [powiązanie](bindable.md) z przykładem użycia **w programie**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Parametr interfejsu, metoda interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|**retval**|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty parametru](parameter-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)<br/>
[określoną](out-cpp.md)
