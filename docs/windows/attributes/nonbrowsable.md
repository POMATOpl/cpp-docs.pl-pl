---
description: 'Dowiedz się więcej na temat: nonbrowsable'
title: nonbrowsable (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonbrowsable
helpviewer_keywords:
- nonbrowsable attribute
ms.assetid: e71a98e7-4b65-454a-9829-342b9f2a84be
ms.openlocfilehash: 943458ff989a3f00d2ce33a4f5681a8bd29a76ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329761"
---
# <a name="nonbrowsable"></a>nonbrowsable

Wskazuje, że element członkowski interfejsu nie powinien być wyświetlany w przeglądarce właściwości.

## <a name="syntax"></a>Składnia

```cpp
[nonbrowsable]
```

## <a name="remarks"></a>Uwagi

Atrybut **nonbrowsable** C++ ma takie same funkcje jak atrybut [nonbrowsable](/windows/win32/Midl/nonbrowsable) MIDL.

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_nonbrowsable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, helpstring("help string"), helpstringcontext(1),
uuid="11111111-1111-1111-1111-111111111111"]
__interface IMyI
{
   [nonbrowsable] HRESULT xx();
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Interface — Metoda|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)
