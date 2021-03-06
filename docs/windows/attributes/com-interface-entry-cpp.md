---
description: 'Dowiedz się więcej na temat: com_interface_entry (C++)'
title: com_interface_entry (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.com_interface_entry
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
ms.openlocfilehash: 2f182149eeac887292391cbb06f625aff261e91f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114888"
---
# <a name="com_interface_entry-c"></a>com_interface_entry (C++)

Dodaje wpis interfejsu do mapy COM klasy docelowej.

## <a name="syntax"></a>Składnia

```cpp
[ com_interface_entry(
  com_interface_entry) ]
```

### <a name="parameters"></a>Parametry

*com_interface_entry*<br/>
Ciąg zawierający rzeczywisty tekst wpisu. Listę możliwych wartości można znaleźć w temacie [COM_INTERFACE_ENTRY MACROS](../../atl/reference/com-interface-entry-macros.md).

## <a name="remarks"></a>Uwagi

**Com_interface_entry** atrybut C++ Wstawia zawartość nieskróconą ciągu znakowego do mapy interfejsu com obiektu docelowego. Jeśli atrybut jest stosowany raz do obiektu docelowego, wpis zostanie wstawiony na początku istniejącej mapy interfejsu. Jeśli atrybut jest stosowany wielokrotnie do tego samego obiektu docelowego, wpisy są wstawiane na początku mapy interfejsu w kolejności, w jakiej zostały odebrane.

Ten atrybut wymaga, aby atrybut [coclass](coclass.md), [ProgID](progid.md)lub [vi_progid](vi-progid.md) (lub inny atrybut, który implikuje jeden z tych) został również zastosowany do tego samego elementu. W przypadku użycia dowolnego pojedynczego atrybutu zostaną automatycznie zastosowane pozostałe dwa. Na przykład, jeśli `progid` jest stosowany, `vi_progid` i `coclass` są również stosowane.

Ponieważ pierwsze użycie **COM_INTERFACE_ENTRY** powoduje, że nowy interfejs zostanie wstawiony na początku mapy interfejsu, musi być jednym z następujących typów COM_INTERFACE_ENTRY:

- COM_INTERFACE_ENTRY

- COM_INTERFACE_ENTRY_IID

- COM_INTERFACE_ENTRY2

- COM_INTERFACE_ENTRY2_IID

Dodatkowe zastosowania atrybutu **COM_INTERFACE_ENTRY** mogą korzystać ze wszystkich obsługiwanych typów COM_INTERFACE_ENTRY.

To ograniczenie jest konieczne, ponieważ ATL używa pierwszego wpisu w mapie interfejsu jako tożsamości; w `IUnknown` związku z tym wpis musi być prawidłowym interfejsem. Na przykład następujący przykładowy kod jest nieprawidłowy, ponieważ pierwszy wpis w mapie interfejsu nie określa rzeczywistego interfejsu COM.

```cpp
[ coclass, com_interface_entry =
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"
]
   class CMyClass
   {
   };
```

## <a name="example"></a>Przykład

Poniższy kod dodaje dwa wpisy do istniejącej mapy interfejsu COM `CMyBaseClass` . Pierwszy jest standardowym interfejsem, a drugi ukrywa `IDebugTest` interfejs.

```cpp
// cpp_attr_ref_com_interface_entry.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name ="ldld")];

[ object,
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]
__interface IDebugTest{};

[ object,
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]
__interface IMyClass{};

[ coclass,
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")
]

class CMyClass: public IMyClass, public IDebugTest
{
};
```

W wyniku mapowania obiektów COM dla programu `CMyBaseClass` jest następująca:

```cpp
BEGIN_COM_MAP(CMyClass)
    COM_INTERFACE_ENTRY (IMyClass)
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)
    COM_INTERFACE_ENTRY(IMyClass)
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)
    COM_INTERFACE_ENTRY(IDebugTest)
    COM_INTERFACE_ENTRY(IProvideClassInfo)
END_COM_MAP()
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **`struct`**|
|**Powtarzalność**|Tak|
|**Wymagane atrybuty**|Co najmniej jeden z następujących elementów: `coclass` , `progid` , lub `vi_progid` .|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty COM](com-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)
