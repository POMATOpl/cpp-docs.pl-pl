---
description: Dowiedz się więcej na temat klasy accelerator_view_removed
title: accelerator_view_removed — klasa
ms.date: 03/27/2019
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::get_view_removed_reason
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
ms.openlocfilehash: 86a5b89d3b8065bccd8eec8b10bade9ed26d6a05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254498"
---
# <a name="accelerator_view_removed-class"></a>accelerator_view_removed — klasa

Wyjątek, który jest generowany, gdy bazowe wywołanie programu DirectX nie powiedzie się z powodu mechanizmu wykrywania i odzyskiwania limitu czasu systemu Windows.

## <a name="syntax"></a>Składnia

```cpp
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor accelerator_view_removed](#ctor)|Inicjuje nowe wystąpienie klasy `accelerator_view_removed`.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|Zwraca kod błędu HRESULT wskazujący przyczynę `accelerator_view` usunięcia obiektu.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amprt. h

**Przestrzeń nazw:** Współbieżności

## <a name="accelerator_view_removed"></a><a name="ctor"></a> accelerator_view_removed

Inicjuje nowe wystąpienie klasy [accelerator_view_removed](accelerator-view-removed-class.md) .

### <a name="syntax"></a>Składnia

```cpp
explicit accelerator_view_removed(
    const char * message,
    HRESULT view_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT view_removed_reason ) throw();
```

### <a name="parameters"></a>Parametry

*Komunikat*<br/>
Opis błędu.

*view_removed_reason*<br/>
Kod błędu HRESULT wskazujący przyczynę usunięcia `accelerator_view` obiektu.

### <a name="return-value"></a>Wartość zwracana

Nowe wystąpienie `accelerator_view_removed` klasy.

## <a name="get_view_removed_reason"></a><a name="get_view_removed_reason"></a> get_view_removed_reason

Zwraca kod błędu HRESULT wskazujący przyczynę `accelerator_view` usunięcia obiektu.

### <a name="syntax"></a>Składnia

```cpp
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
