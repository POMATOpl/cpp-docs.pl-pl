---
description: Dowiedz się więcej na temat klasy time_base
title: time_base — Klasa
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: cad27546109cf8ed6d8314869a3306f238cc6528
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289572"
---
# <a name="time_base-class"></a>time_base — Klasa

Klasa służy jako klasa bazowa dla aspektów szablonu klasy time_get, definiując tylko typ wyliczeniowy `dateorder` i kilka stałych tego typu.

## <a name="syntax"></a>Składnia

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>Uwagi

Każda stała charakteryzuje inny sposób uporządkowania składników daty. Stałe są następujące:

- `no_order` Określa brak określonej kolejności.

- `dmy` określa dzień zamówienia, miesiąc, rok, jak w 2 grudnia 1979.

- `mdy` określa miesiąc zamówienia, dzień, rok, zgodnie z 2 grudnia 1979.

- `ymd` Określa rok zamówienia, miesiąc, dzień, jak w 1979/12/2.

- `ydm` Określa rok zamówienia, dzień, miesiąc, jak w 1979:2 grudnia.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
