---
description: 'Dowiedz się więcej na temat: &lt; &gt; funkcje Chrono'
title: '&lt;&gt;funkcje Chrono'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 161edeccace243c10a6382d931f5f9387f35790d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234205"
---
# <a name="ltchronogt-functions"></a>&lt;&gt;funkcje Chrono

## <a name="duration_cast"></a><a name="duration_cast"></a> duration_cast

Rzutuje `duration` obiekt na określony typ.

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);

template <class ToDuration, class Rep, class Period>
constexpr ToDuration floor(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration ceil(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration round(const duration<Rep, Period>& d);
```

### <a name="return-value"></a>Wartość zwracana

`duration`Obiekt typu `To` , który reprezentuje przedział czasu `Dur` , który jest obcinany, jeśli musi pasować do typu docelowego.

### <a name="remarks"></a>Uwagi

Jeśli `To` jest wystąpieniem `duration` , ta funkcja nie uczestniczy w rozpoznawaniu przeciążenia.

## <a name="time_point_cast"></a><a name="time_point_cast"></a> time_point_cast

Rzutuje obiekt [time_point](../standard-library/time-point-class.md) na określony typ.

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);

template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
floor(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
ceil(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
round(const time_point<Clock, Duration>& tp);
```

### <a name="return-value"></a>Wartość zwracana

`time_point`Obiekt, który ma czas trwania typu `To` .

### <a name="remarks"></a>Uwagi

O ile nie `To` jest wystąpieniem [czasu trwania](../standard-library/duration-class.md), ta funkcja nie uczestniczy w rozpoznawaniu przeciążenia.
