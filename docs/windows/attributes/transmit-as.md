---
description: 'Dowiedz się więcej na temat: transmit_as'
title: transmit_as (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.transmit_as
helpviewer_keywords:
- transmit_as attribute
ms.assetid: 53d0b8ab-5b06-423e-83eb-3d01a10424b2
ms.openlocfilehash: 5f626612257decaf8c7ac6253e3a586b9753deeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329541"
---
# <a name="transmit_as"></a>transmit_as

Instruuje kompilator, aby skojarzyć przedstawiony typ, który obsługuje aplikacje klienta i serwera, z przesyłanym typem.

## <a name="syntax"></a>Składnia

```cpp
[ transmit_as(type) ]
```

### <a name="parameters"></a>Parametry

*Wprowadź*<br/>
Określa typ danych, który jest przesyłany między klientem i serwerem.

## <a name="remarks"></a>Uwagi

Atrybut **transmit_as** C++ ma takie same funkcje jak atrybut [transmit_as](/windows/win32/Midl/transmit-as) MIDL.

## <a name="example"></a>Przykład

Poniższy kod ilustruje użycie atrybutu **transmit_as** :

```cpp
// cpp_attr_ref_transmit_as.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export] typedef struct _TREE_NODE_TYPE {
unsigned short data;
struct _TREE_NODE_TYPE * left;
struct _TREE_NODE_TYPE * right;
} TREE_NODE_TYPE;

[export] struct PACKED_NODE {
   unsigned short data;   // same as normal node
   int index;   // array index of parent
};

// A left node recursive built array of
// the nodes in the tree.  Can be unpacked with
// that knowledge
[export] typedef struct _TREE_XMIT_TYPE {
   int count;
   [size_is(count)] PACKED_NODE node[];
} TREE_XMIT_TYPE;

[transmit_as(TREE_XMIT_TYPE)] typedef TREE_NODE_TYPE * TREE_TYPE;
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`typedef`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[wywozu](export.md)
