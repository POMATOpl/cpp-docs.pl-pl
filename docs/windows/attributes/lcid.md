---
description: 'Dowiedz się więcej o: LCID'
title: LCID (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.lcid
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
ms.openlocfilehash: 2af34574539372a07daadc48874316b0b268f317
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329860"
---
# <a name="lcid"></a>lcid

Umożliwia przekazanie identyfikatora ustawień regionalnych do funkcji.

## <a name="syntax"></a>Składnia

```cpp
[lcid]
```

## <a name="remarks"></a>Uwagi

Atrybut **LCID** języka C++ implementuje funkcje atrybutu [LCID](/windows/win32/Midl/lcid) MIDL. Jeśli chcesz zaimplementować ustawienia regionalne dla bloku biblioteki, użyj parametru **LCID =** `lcid` do atrybutu [modułu](module-cpp.md) .

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_lcid.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];
typedef long HRESULT;

[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]
__interface IStatic {
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Parametr interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty parametru](parameter-attributes.md)
