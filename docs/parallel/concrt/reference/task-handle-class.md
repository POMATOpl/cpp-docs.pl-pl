---
description: Dowiedz się więcej na temat klasy task_handle
title: task_handle — Klasa
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: 21fa2a1782fad200061deb1e85bf052613354a34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188225"
---
# <a name="task_handle-class"></a>task_handle — Klasa

`task_handle`Klasa reprezentuje pojedynczy równoległy element roboczy. Hermetyzuje instrukcje i dane wymagane do wykonania zadania.

## <a name="syntax"></a>Składnia

```cpp
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

### <a name="parameters"></a>Parametry

*_Function*<br/>
Typ obiektu funkcji, który zostanie wywołany do wykonania pracy reprezentowanej przez `task_handle` obiekt.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[task_handle](#task_handle)|Tworzy nowy `task_handle` obiekt. Zadanie jest wykonywane przez wywołanie funkcji określonej jako parametr do konstruktora.|
|[~ task_handle destruktor](#dtor)|Niszczy `task_handle` obiekt.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator ()](#task_handle__operator_call)|Operator wywołania funkcji wywoływany przez środowisko uruchomieniowe w celu wykonania pracy z uchwytem zadania.|

## <a name="remarks"></a>Uwagi

`task_handle` obiekty mogą być używane w połączeniu z `structured_task_group` lub bardziej ogólnym obiektem w celu rozdzielenia `task_group` pracy z zadaniami równoległymi. Aby uzyskać więcej informacji, zobacz [równoległość zadań](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Należy zauważyć, że twórca `task_handle` obiektu jest odpowiedzialny za utrzymanie okresu istnienia utworzonego `task_handle` obiektu, dopóki nie będzie on już wymagany przez środowisko uruchomieniowe współbieżności. Zazwyczaj oznacza to, że `task_handle` obiekt nie może być destruktorem do momentu `wait` wywołania albo metody lub `run_and_wait` , `task_group` `structured_task_group` do której został umieszczony w kolejce.

`task_handle` obiekty są zwykle używane w połączeniu z wyrażeniem lambda języka C++. Ponieważ nie znasz prawdziwego typu lambda, funkcja [make_task](concurrency-namespace-functions.md#make_task) jest zwykle używana do tworzenia `task_handle` obiektu.

Środowisko uruchomieniowe tworzy kopię funkcji pracy przekazanej do `task_handle` obiektu. W związku z tym wszystkie zmiany stanu, które występują w obiekcie funkcji przekazywanym do `task_handle` obiektu nie będą wyświetlane w kopii tego obiektu funkcji.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`task_handle`

## <a name="requirements"></a>Wymagania

**Nagłówek:** PPL. h

**Przestrzeń nazw:** współbieżność

## <a name="operator"></a><a name="task_handle__operator_call"></a> operator ()

Operator wywołania funkcji wywoływany przez środowisko uruchomieniowe w celu wykonania pracy z uchwytem zadania.

```cpp
void operator()() const;
```

## <a name="task_handle"></a><a name="task_handle"></a> task_handle

Tworzy nowy `task_handle` obiekt. Zadanie jest wykonywane przez wywołanie funkcji określonej jako parametr do konstruktora.

```cpp
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Parametry

*_Func*<br/>
Funkcja, która będzie wywoływana w celu wykonania pracy reprezentowanej przez `task_handle` obiekt. Może to być Funktor lambda, wskaźnik do funkcji lub dowolny obiekt obsługujący wersję operatora wywołania funkcji z podpisem `void operator()()` .

### <a name="remarks"></a>Uwagi

Środowisko uruchomieniowe tworzy kopię funkcji pracy przekazanej do konstruktora. W związku z tym wszystkie zmiany stanu, które występują w obiekcie funkcji przekazywanym do `task_handle` obiektu nie będą wyświetlane w kopii tego obiektu funkcji.

## <a name="task_handle"></a><a name="dtor"></a> ~ task_handle

Niszczy `task_handle` obiekt.

```cpp
~task_handle();
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa task_group](task-group-class.md)<br/>
[Klasa structured_task_group](structured-task-group-class.md)
