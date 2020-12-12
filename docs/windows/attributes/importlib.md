---
description: 'Dowiedz się więcej na temat: importlib'
title: importlib (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: f3000be3415ed944d621ebcd36442e33951efc84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114952"
---
# <a name="importlib"></a>importlib

Sprawia, że typy, które zostały już skompilowane w innej bibliotece typów dostępne dla tworzonej biblioteki typów.

## <a name="syntax"></a>Składnia

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>Parametry

*tlb_file*<br/>
Nazwa pliku. tlb, w cudzysłowie, która ma zostać zaimportowana do biblioteki typów w bieżącym projekcie.

## <a name="remarks"></a>Uwagi

Atrybut **importlib** C++ powoduje, że `importlib` instrukcja zostanie umieszczona w bloku biblioteki wygenerowanego pliku IDL. Atrybut **importlib** ma takie same funkcje jak atrybut [importlib](/windows/win32/Midl/importlib) MIDL.

## <a name="example"></a>Przykład

Poniższy kod przedstawia przykład użycia **importlib**:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Dowolne miejsce|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty kompilatora](compiler-attributes.md)<br/>
[Atrybuty autonomiczne](stand-alone-attributes.md)<br/>
[zaimportować](import.md)<br/>
[importidl](importidl.md)<br/>
[być](include-cpp.md)<br/>
[includelib —](includelib-cpp.md)
