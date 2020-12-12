---
description: 'Dowiedz się więcej na temat: library_block'
title: library_block (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 486c40fa8641e74b6e3bc72bc7f980e3ee1216e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329819"
---
# <a name="library_block"></a>library_block

Umieszcza konstrukcję w bloku biblioteki IDL.

## <a name="syntax"></a>Składnia

```cpp
[library_block]
```

## <a name="remarks"></a>Uwagi

Gdy umieszczasz konstrukcję wewnątrz bloku biblioteki, upewnij się, że zostanie ona przeniesiona do biblioteki typów, niezależnie od tego, czy jest przywoływany. Domyślnie tylko konstrukcje modyfikowane przez atrybuty [coclass](coclass.md), [dispinterface](dispinterface.md)i [idl_module](idl-module.md) są umieszczane w bloku biblioteki.

## <a name="example"></a>Przykład

W poniższym kodzie interfejs niestandardowy jest umieszczany wewnątrz bloku biblioteki.

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
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
[Atrybuty autonomiczne](stand-alone-attributes.md)
