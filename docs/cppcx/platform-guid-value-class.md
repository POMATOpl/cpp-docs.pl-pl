---
description: 'Dowiedz się więcej o klasie wartości platform:: GUID'
title: Klasa wartości Platform::Guid
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 4c2ffc5096e6b40266fef0934acc562edf721c24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195193"
---
# <a name="platformguid-value-class"></a>Klasa wartości Platform::Guid

Reprezentuje [GUID] (typ/Windows/Win32/API/guiddef/NS-guiddef-GUID w systemie typu środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
public value struct Guid
```

### <a name="members"></a>Elementy członkowskie

`Platform::Guid` ma `Equals()` metody, `GetHashCode()` i, które `ToString()` pochodzą od [klasy platform:: Object](../cppcx/platform-object-class.md)i `GetTypeCode()` metody pochodnej z [klasy platform:: Type](../cppcx/platform-type-class.md). `Platform::Guid` ma również następujące elementy członkowskie.

|Członek|Opis|
|------------|-----------------|
|[Ident](#ctor)|Inicjuje nowe wystąpienie elementu `Platform::Guid` .|
|[operator = =](#operator-equality)|Equals — operator.|
|[operator! =](#operator-inequality)|Operator not Equals.|
|[zakład&lt;](#operator-less)|Operator mniejszości.|
|[operator ()](#operator-call)|Konwertuje `Platform::Guid` do `GUID` .|

### <a name="remarks"></a>Uwagi

Aby wygenerować nowy `Platform::Guid` , użyj metody statycznej [Windows:: Foundation:: GuidHelper:: CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid) .

### <a name="requirements"></a>Wymagania

**Minimalny obsługiwany klient:** System Windows 8

**Minimalny obsługiwany serwer:** System Windows Server 2012

**Przestrzeń nazw:** Platformach

**Metadane:** obiekt platform. winmd

## <a name="guidguid-constructors"></a><a name="ctor"></a> GUID:: GUID — konstruktory

Inicjuje nowe wystąpienie elementu `Platform::Guid` .

### <a name="syntax"></a>Składnia

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>Parametry

*z*<br/>
Pierwsze 4 bajty `GUID` .

*b*<br/>
Następne 2 bajty `GUID` .

*s*<br/>
Następne 2 bajty `GUID` .

*d*<br/>
Następny bajt `GUID` .

*adres*<br/>
Następny bajt `GUID` .

*n*<br/>
Następny bajt `GUID` .

*g*<br/>
Następny bajt `GUID` .

*h*<br/>
Następny bajt `GUID` .

*i*<br/>
Następny bajt `GUID` .

*j*<br/>
Następny bajt `GUID` .

*k*<br/>
Następny bajt `GUID` .

*m*<br/>
A `GUID` w formie [struktury identyfikatora GUID](/windows/win32/api/guiddef/ns-guiddef-guid).

*n*<br/>
Pozostałe 8 bajtów `GUID` .

## <a name="guidoperator-operator"></a><a name="operator-equality"></a> GUID:: operator = = — operator

Porównuje dwa `Platform::Guid` wystąpienia dla równości.

### <a name="syntax"></a>Składnia

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametry

*guid1*<br/>
Pierwszy `Platform::Guid` do porównania.

*guid2*<br/>
Sekunda `Platform::Guid` do porównania.

### <a name="return-value"></a>Wartość zwracana

Ma wartość true, jeśli dwa `Platform::Guid` wystąpienia są równe.

### <a name="remarks"></a>Uwagi

Preferuj użycie `==` operatora zamiast metody statycznej [Windows:: Foundation:: GuidHelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals) .

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a> GUID:: operator! = — operator

Porównuje dwa `Platform::Guid` wystąpienia pod kątem nierówności.

### <a name="syntax"></a>Składnia

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametry

*guid1*<br/>
Pierwszy `Platform::Guid` do porównania.

*guid2*<br/>
Sekunda `Platform::Guid` do porównania.

### <a name="return-value"></a>Wartość zwracana

Ma wartość true, jeśli dwa `Platform::Guid` wystąpienia nie są równe.

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a> GUID:: operator — &lt; operator

Porównuje dwa `Platform::Guid` wystąpienia do uporządkowania.

### <a name="syntax"></a>Składnia

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametry

*guid1*<br/>
Pierwszy `Platform::Guid` do porównania.

*guid2*<br/>
Sekunda `Platform::Guid` do porównania.

### <a name="return-value"></a>Wartość zwracana

Wartość true, jeśli *guid1* jest uporządkowana przed *guid2*. Porządkowanie jest leksykograficznych po przeprowadzeniu traktowania `Platform::Guid` , tak jakby była tablicą 4 32-bitowych wartości bez znaku. Nie jest to kolejność używana przez SQL Server lub .NET Framework, ani nie jest taka sama jak lexicographical porządkowanie według ciągu.

Ten operator jest dostarczany, aby `Guid` obiekty mogły być łatwiejsze do wykorzystania przez standardową bibliotekę języka C++.

## <a name="guidoperator-operator"></a><a name="operator-call"></a> GUID:: operator () — operator

Niejawnie konwertuje element `Platform::Guid` na [strukturę GUID](/windows/win32/api/guiddef/ns-guiddef-guid).

### <a name="syntax"></a>Składnia

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Wartość zwracana

[Struktura identyfikatora GUID](/windows/win32/api/guiddef/ns-guiddef-guid).

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)
