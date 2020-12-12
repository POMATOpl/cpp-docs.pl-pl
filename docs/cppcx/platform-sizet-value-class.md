---
description: 'Dowiedz się więcej na temat: platform:: Sizeing — Klasa wartości'
title: Klasa wartości Platform::SizeT
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: ebcca27a94d23082374daafaa9fd7db180955a30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308019"
---
# <a name="platformsizet-value-class"></a>Klasa wartości Platform::SizeT

Reprezentuje rozmiar obiektu. Size jest niepodpisanym typem danych.

## <a name="syntax"></a>Składnia

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Elementy członkowskie

|Członek|Opis|
|------------|-----------------|
|[Sized:: size — Konstruktor](#ctor)|Inicjuje nowe wystąpienie klasy z określoną wartością.|

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="sizetsizet-constructor"></a><a name="ctor"></a> Sized:: size — Konstruktor

Inicjuje nowe wystąpienie o rozmiarze o określonej wartości.

### <a name="syntax"></a>Składnia

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Parametry

*sekwencj*<br/>
Niepodpisana wartość 32-bitowa.

*wartość2*<br/>
Wskaźnik do niepodpisanej wartości 32-bitowej.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)
