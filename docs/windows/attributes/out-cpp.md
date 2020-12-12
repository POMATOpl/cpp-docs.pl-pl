---
description: 'Dowiedz się więcej o: out (C++)'
title: out (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: 1984d3bc539c5ad390cc1e507f2c8e3144d96ca2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329702"
---
# <a name="out-c"></a>out (C++)

Identyfikuje parametry wskaźnika, które są zwracane z wywoływanej procedury do procedury wywołującej (z serwera do klienta).

## <a name="syntax"></a>Składnia

```cpp
[out]
```

## <a name="remarks"></a>Uwagi

Atrybut **out** języka C++ ma takie same funkcje jak atrybut [out](/windows/win32/Midl/out-idl) MIDL.

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [powiązania](bindable.md) dla przykładowego użycia **.**

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Parametr interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty parametru](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)
