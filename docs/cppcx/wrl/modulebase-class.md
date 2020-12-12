---
description: 'Dowiedz się więcej na temat: Klasa ModuleBase'
title: ModuleBase — Klasa
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 6540068cee62da5d1a9039a15bcb5bd53ff3aea2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186249"
---
# <a name="modulebase-class"></a>ModuleBase — Klasa

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Uwagi

Reprezentuje klasę bazową klas [modułów](module-class.md) .

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                         | Opis
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase:: ModuleBase](#modulebase)        | Inicjuje wystąpienie klasy `Module`.
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | Deinicjalizuje bieżące wystąpienie `Module` klasy.

### <a name="public-methods"></a>Metody publiczne

Nazwa                                                      | Opis
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::D ecrementObjectCount](#decrementobjectcount) | Po zaimplementowaniu zmniejsza liczbę obiektów śledzonych przez moduł.
[ModuleBase:: IncrementObjectCount —](#incrementobjectcount) | Po zaimplementowaniu zwiększa liczbę obiektów śledzonych przez moduł.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ModuleBase`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a> ModuleBase:: ~ ModuleBase

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Uwagi

Deinicjalizuje bieżące wystąpienie `ModuleBase` klasy.

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a> ModuleBase::D ecrementObjectCount

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Liczba przed operacją zmniejszania.

### <a name="remarks"></a>Uwagi

Po zaimplementowaniu zmniejsza liczbę obiektów śledzonych przez moduł.

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a> ModuleBase:: IncrementObjectCount —

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Liczba przed operacją przyrostu.

### <a name="remarks"></a>Uwagi

Po zaimplementowaniu zwiększa liczbę obiektów śledzonych przez moduł.

## <a name="modulebasemodulebase"></a><a name="modulebase"></a> ModuleBase:: ModuleBase

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Uwagi

Inicjuje wystąpienie klasy `Module`.
