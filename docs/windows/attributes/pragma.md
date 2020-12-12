---
description: 'Dowiedz się więcej na temat: pragma'
title: pragma (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: 1c9b9313b05d5f6b6123189b823ef750cb7c16a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327396"
---
# <a name="pragma"></a>pragma

Emituje określony ciąg do wygenerowanego pliku IDL bez użycia znaków cudzysłowu.

## <a name="syntax"></a>Składnia

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>Parametry

*pragma_statement*<br/>
Pragma, którą chcesz umieścić w wygenerowanym pliku IDL.

## <a name="remarks"></a>Uwagi

Atrybut **pragma** C++ ma takie same funkcje jak atrybut [dyrektywy pragma](/windows/win32/Midl/pragma) MIDL.

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Dowolne miejsce|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty autonomiczne](stand-alone-attributes.md)<br/>
[pakiet](../../preprocessor/pack.md)
