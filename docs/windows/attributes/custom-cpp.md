---
description: 'Dowiedz się więcej o: niestandardowym (C++)'
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 7771230fd6eed5f567fb2e74e8cd869a0b3618f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333146"
---
# <a name="custom-c"></a>custom (C++)

Definiuje metadane dla obiektu w bibliotece typów.

## <a name="syntax"></a>Składnia

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>Parametry

*uuid*<br/>
Unikatowy identyfikator.

*wartość*<br/>
Wartość, która może zostać wprowadzona do wariantu.

## <a name="remarks"></a>Uwagi

**Niestandardowy** atrybut C++ spowoduje umieszczenie informacji w bibliotece typów. Wymagane jest narzędzie, które odczytuje wartość niestandardową z biblioteki typów.

Atrybut **niestandardowy** ma taką samą funkcjonalność jak [niestandardowy](/windows/win32/Midl/custom) atrybut MIDL.

## <a name="requirements"></a>Wymagania

### <a name="attribute-context"></a>Kontekst atrybutu

- **Dotyczy**: nie com `interface` , `idl_module` metod, elementów członkowskich interfejsu, parametrów interfejsu,,,,, **`typedef`** **`class`** **`enum`** **`union`** i **`struct`** typów.
- **Powtarzalne**: tak.
- **Wymagane atrybuty**: **coclass** (gdy jest używana w klasie).
- **Nieprawidłowe atrybuty**: Brak.

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty autonomiczne](stand-alone-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Atrybuty parametru](parameter-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)
