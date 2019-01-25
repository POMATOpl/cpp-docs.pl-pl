---
title: HandleT — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: 6e5824da03fb85e52f413f5678ea6e0fd6c77ddd
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335001"
---
# <a name="handlet-class"></a>HandleT — Klasa

Reprezentuje uchwyt do obiektu.

## <a name="syntax"></a>Składnia

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Parametry

*Handletraits —*<br/>
Wystąpienie [handletraits —](handletraits-structure.md) stucture, który definiuje typowe cechy dojście.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa     | Opis
-------- | -----------------------------
`Traits` | Synonim dla `HandleTraits`.

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                | Opis
----------------------------------- | --------------------------------------------------
[HandleT::HandleT](#handlet)        | Inicjuje nowe wystąpienie klasy `HandleT` klasy.
[HandleT::~HandleT](#tilde-handlet) | Wyłącza wystąpienie `HandleT` klasy.

### <a name="public-methods"></a>Metody publiczne

Nazwa                         | Opis
---------------------------- | ----------------------------------------------------------------------
[HandleT::Attach](#attach)   | Kojarzy określone dojście z bieżącego `HandleT` obiektu.
[HandleT::Close](#close)     | Zamyka bieżące `HandleT` obiektu.
[HandleT::Detach](#detach)   | Powoduje usunięcie bieżącego `HandleT` obiekt z jego podstawowego dojścia.
[HandleT::Get](#get)         | Pobiera wartość podstawowego dojścia.
[HandleT::IsValid](#isvalid) | Wskazuje, czy bieżący `HandleT` obiekt reprezentuje dojście.

### <a name="protected-methods"></a>Metody chronione

Nazwa                                     | Opis
---------------------------------------- | ------------------------------------
[HandleT::InternalClose](#internalclose) | Zamyka bieżące `HandleT` obiektu.

### <a name="public-operators"></a>Operatory publiczne

Nazwa                                   | Opis
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT::operator =](#operator-assign) | Przenosi wartość określonego `HandleT` obiekt do bieżącego `HandleT` obiektu.

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

Nazwa                        | Opis
--------------------------- | ----------------------------------------------------------------
[HandleT::handle_](#handle) | Zawiera uchwyt, który jest reprezentowany przez `HandleT` obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`HandleT`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers.h

**Namespace:** Microsoft::wrl:: wrappers

## <a name="tilde-handlet"></a>HandleT::~HandleT

Wyłącza wystąpienie `HandleT` klasy.

```cpp
~HandleT();
```

## <a name="attach"></a>HandleT::Attach

Kojarzy określone dojście z bieżącego `HandleT` obiektu.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Dojście.

## <a name="close"></a>HandleT::Close

Zamyka bieżące `HandleT` obiektu.

```cpp
void Close();
```

### <a name="remarks"></a>Uwagi

Dojście, która jest podporządkowana narzędziu bieżącego `HandleT` jest zamknięte, a `HandleT` ustawiono nieprawidłowy stan.

Jeśli uchwyt nie zamyka się prawidłowo, tworzony jest wyjątek w wątku wywołującego.

## <a name="detach"></a>HandleT::Detach

Powoduje usunięcie bieżącego `HandleT` obiekt z jego podstawowego dojścia.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Wartość zwracana

Podstawowego dojścia.

### <a name="remarks"></a>Uwagi

Po zakończeniu tej operacji, bieżący `HandleT` ustawiono nieprawidłowy stan.

## <a name="get"></a>HandleT::Get

Pobiera wartość podstawowego dojścia.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Wartość zwracana

Dojście.

## <a name="handle"></a>HandleT::handle_

Zawiera uchwyt, który jest reprezentowany przez `HandleT` obiektu.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>HandleT::HandleT

Inicjuje nowe wystąpienie klasy `HandleT` klasy.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Dojście.

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor inicjuje `HandleT` obiekt, który nie jest prawidłowy uchwyt do obiektu. Drugi Konstruktor tworzy nową `HandleT` obiektu z parametru *h*.

## <a name="internalclose"></a>HandleT::InternalClose

Zamyka bieżące `HandleT` obiektu.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Wartość zwracana

**wartość true,** Jeśli bieżące `HandleT` zamknięta pomyślnie; w przeciwnym razie **false**.

### <a name="remarks"></a>Uwagi

`InternalClose()` jest `protected`.

## <a name="isvalid"></a>HandleT::IsValid

Wskazuje, czy bieżący `HandleT` obiekt reprezentuje dojście.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

**wartość true,** Jeśli `HandleT` reprezentuje uchwyt; w przeciwnym razie **false**.

## <a name="operator-assign"></a>HandleT::operator =

Przenosi wartość określonego `HandleT` obiekt do bieżącego `HandleT` obiektu.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Odwołanie rvalue do uchwytu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do bieżącego `HandleT` obiektu.

### <a name="remarks"></a>Uwagi

Ta operacja powoduje unieważnienie `HandleT` obiekt określony przez parametr *h*.