---
description: 'Dowiedz się więcej na temat: Klasa RoInitializeWrapper'
title: RoInitializeWrapper — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: b7f2c49bd461f08ad732680f1a02968ee7717116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319303"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper — Klasa

Inicjuje środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Uwagi

`RoInitializeWrapper` jest wygodą, która inicjuje środowisko wykonawcze systemu Windows i zwraca wartość HRESULT, która wskazuje, czy operacja zakończyła się pomyślnie. Ponieważ destruktor klasy wywołuje `::Windows::Foundation::Uninitialize` , wystąpienia elementu `RoInitializeWrapper` muszą być zadeklarowane w zakresie globalnym lub najwyższego poziomu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                                                    | Opis
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper:: RoInitializeWrapper](#roinitializewrapper)        | Inicjuje nowe wystąpienie klasy `RoInitializeWrapper`.
[RoInitializeWrapper:: ~ RoInitializeWrapper](#tilde-roinitializewrapper) | Niszczy bieżące wystąpienie `RoInitializeWrapper` klasy.

### <a name="public-operators"></a>Operatory publiczne

Nazwa                                       | Opis
------------------------------------------ | ------------------------------------------------------------------------
[RoInitializeWrapper:: HRESULT ()](#hresult) | Pobiera wartość HRESULT wygenerowaną przez `RoInitializeWrapper` Konstruktor.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`RoInitializeWrapper`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a> RoInitializeWrapper:: HRESULT ()

Pobiera wartość HRESULT wygenerowaną przez ostatniego `RoInitializeWrapper` konstruktora.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a> RoInitializeWrapper:: RoInitializeWrapper

Inicjuje nowe wystąpienie klasy `RoInitializeWrapper`.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>Parametry

*znaczników*<br/>
Jedno z wyliczeń RO_INIT_TYPE, które określa pomoc techniczną dostarczoną przez środowisko wykonawcze systemu Windows.

### <a name="remarks"></a>Uwagi

`RoInitializeWrapper`Klasa wywołuje `Windows::Foundation::Initialize(flags)` .

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a> RoInitializeWrapper:: ~ RoInitializeWrapper

Odinicjuje środowisko wykonawcze systemu Windows.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>Uwagi

`RoInitializeWrapper`Klasa wywołuje `Windows::Foundation::Uninitialize()` .
