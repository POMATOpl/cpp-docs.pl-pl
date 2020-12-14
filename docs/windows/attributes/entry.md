---
description: 'Dowiedz się więcej na temat: wprowadzanie'
title: entry (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: fbceea4c23d730ceba780ce68398a9d78fa9c33b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259230"
---
# <a name="entry"></a>entry

Określa wyeksportowaną funkcję lub stałą w module, identyfikując punkt wejścia w bibliotece DLL.

## <a name="syntax"></a>Składnia

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Parametry

*id*<br/>
Identyfikator punktu wejścia.

## <a name="remarks"></a>Uwagi

**Wpis** C++ Attribute ma takie same funkcje jak atrybut MIDL [wpisu](/windows/win32/Midl/entry) .

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [idl_module](idl-module.md) , aby zapoznać się z przykładem zastosowania **wpisów**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Atrybut `idl_module`|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)
