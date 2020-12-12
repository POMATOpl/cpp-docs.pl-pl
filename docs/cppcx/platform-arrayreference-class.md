---
description: 'Dowiedz się więcej na temat: platform:: ArrayReference, Klasa'
title: 'Platform:: ArrayReference, Klasa'
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: 6d883dd369b4b439bd02a337017e8c13731999d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284086"
---
# <a name="platformarrayreference-class"></a>Platform:: ArrayReference, Klasa

`ArrayReference` jest typem optymalizacji, który można zastąpić dla [platform:: Array ^](../cppcx/platform-array-class.md) w parametrach wejściowych, gdy chcesz wypełnić tablicę w stylu C danymi wejściowymi.

## <a name="syntax"></a>Składnia

```cpp
class ArrayReference
```

### <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ArrayReference::ArrayReference](#ctor)|Inicjuje nowe wystąpienie klasy `ArrayReference`.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ArrayReference:: operator () — operator](#operator-call)|Konwertuje ten `ArrayReference` element na `Platform::Array<T>^*` .|
|[ArrayReference:: operator = — operator](#operator-assign)|Przypisuje zawartość innego `ArrayReference` do tego wystąpienia.|

## <a name="exceptions"></a>Wyjątki

### <a name="remarks"></a>Uwagi

Używając `ArrayReference` do wypełniania tablicy w stylu c, można uniknąć operacji dodatkowej kopiowania, która będzie dotyczyła kopiowania najpierw do `Platform::Array` zmiennej, a następnie do tablicy w stylu C. W przypadku korzystania `ArrayReference` z programu istnieje tylko jedna operacja kopiowania. Aby zapoznać się z przykładem kodu, zobacz [Array i WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Nagłówek:** vccorlib. h

## <a name="arrayreferencearrayreference-constructor"></a><a name="ctor"></a> ArrayReference:: ArrayReference — Konstruktor

Inicjuje nowe wystąpienie klasy [platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) .

### <a name="syntax"></a>Składnia

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>Parametry

*dataArg*<br/>
Wskaźnik do danych macierzy.

*sizeArg*<br/>
Liczba elementów w tablicy źródłowej.

*otherArg*<br/>
`ArrayReference`Obiekt, którego dane zostaną przeniesione, aby zainicjować nowe wystąpienie.

### <a name="remarks"></a>Uwagi

## <a name="arrayreferenceoperator-operator"></a><a name="operator-assign"></a> ArrayReference:: operator = — operator

Przypisuje określony obiekt do bieżącego obiektu [platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) przy użyciu semantyki przenoszenia.

### <a name="syntax"></a>Składnia

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Parametry

*otherArg*<br/>
Obiekt, który jest przenoszony do bieżącego `ArrayReference` obiektu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do obiektu typu `ArrayReference` .

### <a name="remarks"></a>Uwagi

`Platform::ArrayReference` jest standardowym szablonem klasy języka C++, a nie klasą referencyjną.

## <a name="arrayreferenceoperator-operator"></a><a name="operator-call"></a> ArrayReference:: operator () — operator

Konwertuje bieżący obiekt [platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) z powrotem na klasę [platform:: Array](../cppcx/platform-array-class.md) .

### <a name="syntax"></a>Składnia

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Wartość zwracana

Dojście do obiektu typu `Array<TArg>^`

### <a name="remarks"></a>Uwagi

[Platform:: ArrayReference](../cppcx/platform-arrayreference-class.md) jest standardowym szablonem klasy języka C++, a [platform:: Array](../cppcx/platform-array-class.md) jest klasą ref.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)
