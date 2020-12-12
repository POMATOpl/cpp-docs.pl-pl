---
description: 'Dowiedz się więcej o: nierozszerzalny'
title: nierozszerzalny (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: dfb0eda0fc8c6de367ee29ec3786750ba40395ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327449"
---
# <a name="nonextensible"></a>nonextensible

Określa, że `IDispatch` implementacja zawiera tylko właściwości i metody wymienione w opisie interfejsu i nie można go rozszerzyć z dodatkowymi elementami członkowskimi w czasie wykonywania.

## <a name="syntax"></a>Składnia

```cpp
[nonextensible]
```

## <a name="remarks"></a>Uwagi

Atrybut **nierozszerzalny** C++ ma taką samą funkcjonalność jak atrybut [nierozszerzalny](/windows/win32/Midl/nonextensible) MIDL.

Użycie **nierozszerzalne** wymaga również atrybutu [OleAutomation](oleautomation.md) .

## <a name="example"></a>Przykład

Poniższy kod pokazuje jedno użycie atrybutu **nierozszerzalny** :

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejsu**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|`dual` i `oleautomation` lub `dispinterface`|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)
