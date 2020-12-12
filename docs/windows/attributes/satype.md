---
description: 'Dowiedz się więcej na temat: satype'
title: satype (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: dab0f866eba5501a9a83d531d9cbdf50501dcff0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327318"
---
# <a name="satype"></a>satype

Określa typ danych `SAFEARRAY` struktury.

## <a name="syntax"></a>Składnia

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>Parametry

*data_type*<br/>
Typ danych dla `SAFEARRAY` struktury danych, która jest przesyłana jako parametr do metody interfejsu.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Parametr interfejsu, metoda interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

## <a name="remarks"></a>Uwagi

Atrybut **satype** C++ określa typ danych `SAFEARRAY` .

> [!NOTE]
> Poziom pośredni został porzucony ze `SAFEARRAY` wskaźnika w wygenerowanym pliku. idl od sposobu zadeklarowania w pliku. cpp.

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>Zobacz także

[Atrybuty kompilatora](compiler-attributes.md)<br/>
[Atrybuty parametru](parameter-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[id](id.md)
