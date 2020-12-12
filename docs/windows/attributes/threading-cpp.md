---
description: 'Dowiedz się więcej o: wątking (C++)'
title: Threading (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: e46a3720280fe7ee7b9debae98e3270825e8db40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327258"
---
# <a name="threading-c"></a>threading (C++)

Określa model wątkowości dla obiektu COM.

## <a name="syntax"></a>Składnia

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Parametry

*wzorów*<br/>
Obowiązkowe Jeden z następujących modeli wątkowości:

- `apartment` (wątkowość apartamentu)

- `neutral` (Składniki .NET Framework bez interfejsu użytkownika)

- `single` (prosta wątkowość)

- `free` (bezpłatna wątkowość)

- `both` (Apartment i Free Threading)

Wartość domyślna to `apartment`.

## <a name="remarks"></a>Uwagi

Atrybut **Threading** języka C++ nie jest wyświetlany w wygenerowanym pliku IDL, ale zostanie użyty w implementacji obiektu com.

W projektach ATL, jeśli istnieje również atrybut [klasy coclass](coclass.md) , model wątkowości określony przez *model* jest przenoszona jako parametr szablonu do klasy [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) , wstawiany przez `coclass` atrybut.

Atrybut **wątkowości** chroni również dostęp do [event_source](event-source.md).

## <a name="example"></a>Przykład

Zapoznaj się z [licencjonowanym](licensed.md) przykładem użycia **wątku**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **`struct`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|**coclass**|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty COM](com-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Obsługa wielowątkowości w przypadku starszego kodu (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Neutralny apartamentach](/windows/win32/cossdk/neutral-apartments)
