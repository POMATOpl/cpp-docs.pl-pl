---
description: 'Dowiedz się więcej na temat: vi_progid'
title: vi_progid (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: 766ebcee636b3fb0bcdb1aeabd53ee0e977ca790
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327190"
---
# <a name="vi_progid"></a>vi_progid

Określa niezależną od wersji identyfikator ProgID.

## <a name="syntax"></a>Składnia

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Parametry

*Nazwij*<br/>
Niezależny od wersji identyfikator ProgID reprezentujący obiekt.

Identyfikatory ProgID składają się na czytelną dla człowieka wersję identyfikatora klasy (CLSID) służącą do identyfikowania obiektów COM/ActiveX.

## <a name="remarks"></a>Uwagi

Atrybut **vi_progid** C++ umożliwia określenie identyfikatora ProgID niezależnego od wersji dla obiektu com. Identyfikator ProgID ma postać *Name1. NAME2. Version*. Niezależny od wersji ProgID nie ma *wersji*. Możliwe jest określenie zarówno `progid` atrybutów, jak i **vi_progid** na `coclass` . Jeśli nie określisz **vi_progid**, program ProgID niezależny od wersji jest wartością określoną przez atrybut [ProgID](progid.md) .

**vi_progid** implikuje `coclass` atrybut, oznacza to, że jeśli określisz **vi_progid**, jest to takie samo, jak określenie `coclass` atrybutów i **vi_progid** .

Atrybut **vi_progid** powoduje automatyczne zarejestrowanie klasy pod określoną nazwą. Wygenerowany plik IDL nie będzie wyświetlał wartości ProgID.

W projektach ATL, jeśli atrybut [klasy coclass](coclass.md) jest również obecny, określony ProgID jest używany przez `GetVersionIndependentProgID` funkcję (wstawioną przez `coclass` atrybut).

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [klasy coclass](coclass.md) dla przykładowego użycia **vi_progid**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **`struct`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[Klucz ProgID](/windows/win32/com/-progid--key)
