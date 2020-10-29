---
title: Klasa EventStack
description: Odwołanie do klasy EventStack zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4f1e92011acdf8272fe631843c03c2f960a1234
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920713"
---
# <a name="eventstack-class"></a>Klasa EventStack

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`EventStack`Klasa jest kolekcją obiektów [zdarzeń](event.md) . Wszystkie zdarzenia otrzymane z zestawu SDK usługi Build Insights są dostępne w postaci `EventStack` obiektu. Ostatni wpis w tym stosie jest aktualnie przetwarzanym zdarzeniem. Wpisy poprzedzające ostatni wpis są hierarchią nadrzędną bieżącego zdarzenia. Aby uzyskać więcej informacji na temat modelu zdarzeń używanego w usłudze C++ build Insights, zobacz [tabela zdarzeń](../event-table.md).

## <a name="syntax"></a>Składnia

```cpp
class EventStack
{
public:
    EventStack(const EVENT_COLLECTION_DATA& data);

    size_t      Size() const;
    RawEvent    Back() const;
    RawEvent    operator[] (size_t index) const;
};
```

## <a name="members"></a>Elementy członkowskie

### <a name="constructors"></a>Konstruktory

[EventStack](#event-stack)

### <a name="functions"></a>Funkcje

[Wstecz](#back) 
 [operator []](#subscript-operator) 
 [Rozmiar](#size)

## <a name="back"></a><a name="back"></a> Wstecz

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Wartość zwracana

Obiekt [RawEvent](raw-event.md) , który reprezentuje ostatni wpis w stosie. Ostatnim wpisem w stosie zdarzeń jest zdarzenie, które zostało wyzwolone.

## <a name="eventstack"></a><a name="event-stack"></a> EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>Parametry

*Data*\
Dane pierwotne, z których `EventStack` została utworzona.

### <a name="remarks"></a>Uwagi

Zazwyczaj nie trzeba tworzyć `EventStack` obiektów samodzielnie. Są one udostępniane przez zestaw SDK usługi Build Insights, gdy zdarzenia są przetwarzane podczas przeprowadzania analizy lub ponownego rejestrowania sesji.

## <a name="operator"></a><a name="subscript-operator"></a> operator []

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>Parametry

*indeks*\
Indeks elementu, do którego można uzyskać dostęp w stosie zdarzeń.

### <a name="return-value"></a>Wartość zwracana

Obiekt [RawEvent](raw-event.md) , który reprezentuje zdarzenie przechowywane w pozycji wskazywanej przez *indeks* w stosie zdarzeń.

## <a name="size"></a><a name="size"></a> Zmienia

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar stosu zdarzeń.

::: moniker-end
