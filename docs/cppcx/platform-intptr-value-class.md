---
description: 'Dowiedz się więcej o klasie wartości platform:: IntPtr'
title: Klasa wartości Platform::IntPtr
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
ms.openlocfilehash: 18c5316eaae84b1e6af4e54d86ef876d81a866ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295266"
---
# <a name="platformintptr-value-class"></a>Klasa wartości Platform::IntPtr

Reprezentuje podpisany wskaźnik lub dojście, którego rozmiar jest specyficzny dla platformy (32-bitowy lub 64-bitowy).

## <a name="syntax"></a>Składnia

```cpp
public value struct IntPtr
```

### <a name="members"></a>Elementy członkowskie

Element IntPtr ma następujących członków:

|Członek|Opis|
|------------|-----------------|
|[IntPtr:: IntPtr](#ctor)|Inicjuje nowe wystąpienie elementu IntPtr.|
|[IntPtr:: op_explicit — operator](#op-explicit)|Konwertuje określony parametr na element IntPtr lub wskaźnik na wartość IntPtr.|
|[IntPtr:: Toint32 —](#toint32)|Konwertuje bieżący IntPtr na 32-bitową liczbę całkowitą.|

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="intptrintptr-constructor"></a><a name="ctor"></a> IntPtr:: IntPtr, Konstruktor

Inicjuje nowe wystąpienie elementu IntPtr o określonej wartości.

### <a name="syntax"></a>Składnia

```cpp
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
64-bitowy uchwyt lub wskaźnik lub wskaźnik do wartości 64-bitowej lub wartość 32-bitową, która może zostać przekonwertowana na wartość 64-bitową.

## <a name="intptrop_explicit-operator"></a><a name="op-explicit"></a> IntPtr:: Op_explicit — operator

Konwertuje określony parametr na element IntPtr lub wskaźnik na wartość IntPtr.

### <a name="syntax"></a>Składnia

```cpp
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );
```

### <a name="parameters"></a>Parametry

*sekwencj*<br/>
Wskaźnik do uchwytu lub IntPtr.

*wartość2*<br/>
32-bitowa liczba całkowita, która może zostać przekonwertowana na IntPtr.

*Wartość3*<br/>
Element IntPtr.

### <a name="return-value"></a>Wartość zwracana

Pierwszy i drugi Operator zwracają element IntPtr. Trzeci operator zwraca wskaźnik do wartości reprezentowanej przez bieżący element IntPtr.

## <a name="intptrtoint32-method"></a><a name="toint32"></a> IntPtr:: Toint32 —, Metoda

Konwertuje bieżącą wartość IntPtr na 32-bitową liczbę całkowitą.

### <a name="syntax"></a>Składnia

```cpp
int32 IntPtr::ToInt32();
```

### <a name="return-value"></a>Wartość zwracana

32-bitowa liczba całkowita.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)
