---
description: 'Dowiedz się więcej na temat: Klasa CHandle'
title: Klasa CHandle
ms.date: 07/09/2019
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
ms.openlocfilehash: 01c3b281daf829bc6488df35114c6cb853640ed1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141677"
---
# <a name="chandle-class"></a>Klasa CHandle

Ta klasa dostarcza metody do tworzenia i używania obiektu uchwytu.

## <a name="syntax"></a>Składnia

```
class CHandle
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHandle::CHandle](#chandle)|Konstruktor.|
|[CHandle:: ~ CHandle](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHandle:: Attach](#attach)|Wywołaj tę metodę, aby dołączyć `CHandle` obiekt do istniejącego dojścia.|
|[CHandle:: Close](#close)|Wywołaj tę metodę, aby zamknąć `CHandle` obiekt.|
|[CHandle::D etach](#detach)|Wywołaj tę metodę, aby odłączyć dojście z `CHandle` obiektu.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHandle:: uchwyt operatora](#operator_handle)|Zwraca wartość przechowywanego dojścia.|
|[CHandle:: operator =](#operator_eq)|Operator przypisania.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CHandle:: m_h](#m_h)|Zmienna członkowska, która przechowuje uchwyt.|

## <a name="remarks"></a>Uwagi

`CHandle`Obiektu można używać zawsze, gdy wymagane jest dojście: główna różnica polega na tym, że `CHandle` obiekt zostanie automatycznie usunięty.

> [!NOTE]
> Niektóre funkcje interfejsu API będą używać wartości NULL jako pustego lub nieprawidłowego dojścia, podczas gdy inne używają INVALID_HANDLE_VALUE. `CHandle` używa tylko wartości NULL i traktuje INVALID_HANDLE_VALUE jako realne dojście. W przypadku wywołania interfejsu API, który może zwracać INVALID_HANDLE_VALUE, należy sprawdzić tę wartość przed wywołaniem elementu [CHandle:: Attach](#attach) lub przekazanie go do `CHandle` konstruktora, a zamiast tego przekazać wartość null.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="chandleattach"></a><a name="attach"></a> CHandle:: Attach

Wywołaj tę metodę, aby dołączyć `CHandle` obiekt do istniejącego dojścia.

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>Parametry

*h*<br/>
`CHandle` przejdzie na własność dojścia *h*.

### <a name="remarks"></a>Uwagi

Przypisuje `CHandle` obiekt do dojścia *h* , a następnie wywołuje **h. Odłącz ()**. W kompilacjach debugowania program ATLASSERT zostanie zgłoszony, jeśli *h* ma wartość null. Nie jest wykonywane żadne inne sprawdzenie ważności dojścia.

## <a name="chandlechandle"></a><a name="chandle"></a> CHandle::CHandle

Konstruktor.

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>Parametry

*h*<br/>
Istniejący uchwyt lub `CHandle` .

### <a name="remarks"></a>Uwagi

Tworzy nowy `CHandle` obiekt, opcjonalnie używając istniejącego uchwytu lub `CHandle` obiektu.

## <a name="chandlechandle"></a><a name="dtor"></a> CHandle:: ~ CHandle

Destruktor.

```
~CHandle() throw();
```

### <a name="remarks"></a>Uwagi

Zwalnia `CHandle` obiekt przez wywołanie [CHandle:: Close](#close).

## <a name="chandleclose"></a><a name="close"></a> CHandle:: Close

Wywołaj tę metodę, aby zamknąć `CHandle` obiekt.

```cpp
void Close() throw();
```

### <a name="remarks"></a>Uwagi

Zamyka dojście do otwartego obiektu. Jeśli dojście ma wartość NULL, co będzie miało miejsce, jeśli `Close` zostało już wywołane, ATLASSERT zostanie zgłoszone w kompilacjach debugowania.

## <a name="chandledetach"></a><a name="detach"></a> CHandle::D etach

Wywołaj tę metodę, aby odłączyć dojście z `CHandle` obiektu.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca odłączenie dojścia.

### <a name="remarks"></a>Uwagi

Zwalnia własność dojścia.

## <a name="chandlem_h"></a><a name="m_h"></a> CHandle:: m_h

Zmienna członkowska, która przechowuje uchwyt.

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a> CHandle:: operator =

Operator przypisania.

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>Parametry

*h*<br/>
`CHandle` przejdzie na własność dojścia *h*.

### <a name="return-value"></a>Wartość zwracana

Zwraca odwołanie do nowego `CHandle` obiektu.

### <a name="remarks"></a>Uwagi

Jeśli `CHandle` obiekt zawiera obecnie uchwyt, zostanie zamknięty. Obiekt, który `CHandle` jest przesyłany, będzie miał odwołanie do dojścia ustawione na wartość null. Dzięki temu dwa `CHandle` obiekty nigdy nie będą zawierać tego samego aktywnego uchwytu.

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a> CHandle:: uchwyt operatora

Zwraca wartość przechowywanego dojścia.

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>Uwagi

Zwraca wartość przechowywaną w [CHandle:: m_h](#m_h).

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
