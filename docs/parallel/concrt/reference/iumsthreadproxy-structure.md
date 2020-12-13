---
description: Dowiedz się więcej o strukturze IUMSThreadProxy
title: IUMSThreadProxy — Struktura
ms.date: 11/04/2016
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
ms.openlocfilehash: 02eb999b35143e4fc9e0416e02abb60c3c64768d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334320"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy — Struktura

Abstrakcja wątku wykonania. Jeśli chcesz, aby harmonogram przyznał wątki harmonogramie (UMS), ustaw wartość dla elementu zasady harmonogramu `SchedulerKind` na `UmsThreadDefault` , a następnie Zaimplementuj `IUMSScheduler` interfejs. Wątki UMS są obsługiwane tylko w 64-bitowych systemach operacyjnych z wersją Windows 7 i nowszą.

## <a name="syntax"></a>Składnia

```cpp
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IUMSThreadProxy:: EnterCriticalRegion —](#entercriticalregion)|Wywoływana w celu wprowadzenia regionu krytycznego. W ramach regionu krytycznego harmonogram nie będzie obserwować asynchronicznych operacji blokowania, które są wykonywane w danym regionie. Oznacza to, że harmonogram nie zostanie ponownie wprowadzony dla błędów strony, zawieszeń wątku, asynchronicznych wywołań procedur jądra (APCs) i tak dalej, dla wątku UMS.|
|[IUMSThreadProxy:: EnterHyperCriticalRegion —](#enterhypercriticalregion)|Wywoływana w celu wprowadzenia regionu krytycznego dla funkcji Hyper-in. W regionie o krytycznym znaczeniu dla funkcji harmonogram nie będzie obserwować żadnych operacji blokowania, które są wykonywane w danym regionie. Oznacza to, że harmonogram nie zostanie ponownie wprowadzony w celu zablokowania wywołań funkcji, blokady zawieszania, które blokują, błędy stron, zawieszenia wątku, asynchroniczne wywołania procedur jądra (APCs) i tak dalej, dla wątku UMS.|
|[IUMSThreadProxy:: ExitCriticalRegion —](#exitcriticalregion)|Wywoływana w celu opuszczenia regionu krytycznego.|
|[IUMSThreadProxy:: ExitHyperCriticalRegion —](#exithypercriticalregion)|Wywołuje się, by wyjść z regionu krytycznego dla funkcji Hyper-krytyczny.|
|[IUMSThreadProxy:: GetCriticalRegionType —](#getcriticalregiontype)|Zwraca rodzaj regionu krytycznego, w którym znajduje się serwer proxy wątku. Ze względu na to, że regiony krytyczne dla funkcji Hyper są nadzbiorem regionów krytycznych, w przypadku wprowadzenia kodu do regionu krytycznego, a następnie do regionu krytycznego dla funkcji Hyper, `InsideHyperCriticalRegion` zostaną zwrócone.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Wymagania

**Nagłówek:** concrtrm. h

**Przestrzeń nazw:** współbieżność

## <a name="iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a> IUMSThreadProxy:: EnterCriticalRegion —, Metoda

Wywoływana w celu wprowadzenia regionu krytycznego. W ramach regionu krytycznego harmonogram nie będzie obserwować asynchronicznych operacji blokowania, które są wykonywane w danym regionie. Oznacza to, że harmonogram nie zostanie ponownie wprowadzony dla błędów strony, zawieszeń wątku, asynchronicznych wywołań procedur jądra (APCs) i tak dalej, dla wątku UMS.

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Nowa głębokość regionu krytycznego. Obszary krytyczne są współużytkowane.

## <a name="iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a> IUMSThreadProxy:: EnterHyperCriticalRegion —, Metoda

Wywoływana w celu wprowadzenia regionu krytycznego dla funkcji Hyper-in. W regionie o krytycznym znaczeniu dla funkcji harmonogram nie będzie obserwować żadnych operacji blokowania, które są wykonywane w danym regionie. Oznacza to, że harmonogram nie zostanie ponownie wprowadzony w celu zablokowania wywołań funkcji, blokady zawieszania, które blokują, błędy stron, zawieszenia wątku, asynchroniczne wywołania procedur jądra (APCs) i tak dalej, dla wątku UMS.

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Nowa głębokość regionu krytycznego dla funkcji Hyper-lokacja. Regiony krytyczne dla funkcji Hyper są współużytkowane.

### <a name="remarks"></a>Uwagi

Harmonogram musi być bardzo ostrożnie na temat metod wywoływanych przez nią i blokad, które są w tych regionach. Jeśli kod w tym regionie blokuje blokadę, która jest utrzymywana przez coś, że harmonogram jest odpowiedzialny za planowanie, zakleszczenie może nastąpić.

## <a name="iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a> IUMSThreadProxy:: ExitCriticalRegion —, Metoda

Wywoływana w celu opuszczenia regionu krytycznego.

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Nowa głębokość regionu krytycznego. Obszary krytyczne są współużytkowane.

## <a name="iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a> IUMSThreadProxy:: ExitHyperCriticalRegion —, Metoda

Wywołuje się, by wyjść z regionu krytycznego dla funkcji Hyper-krytyczny.

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Nowa głębokość regionu krytycznego dla funkcji Hyper-lokacja. Regiony krytyczne dla funkcji Hyper są współużytkowane.

## <a name="iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a> IUMSThreadProxy:: GetCriticalRegionType —, Metoda

Zwraca rodzaj regionu krytycznego, w którym znajduje się serwer proxy wątku. Ze względu na to, że regiony krytyczne dla funkcji Hyper są nadzbiorem regionów krytycznych, w przypadku wprowadzenia kodu do regionu krytycznego, a następnie do regionu krytycznego dla funkcji Hyper, `InsideHyperCriticalRegion` zostaną zwrócone.

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Wartość zwracana

Typ regionu krytycznego, w którym znajduje się serwer proxy wątku.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Struktura IUMSScheduler](iumsscheduler-structure.md)
