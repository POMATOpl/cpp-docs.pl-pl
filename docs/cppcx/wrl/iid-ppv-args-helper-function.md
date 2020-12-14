---
description: 'Dowiedz się więcej o: funkcja IID_PPV_ARGS_Helper'
title: IID_PPV_ARGS_Helper — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 7003a3270a6fdb2070055e0059b106f55324c63e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229148"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper — Funkcja

Sprawdza, czy typ określonego argumentu pochodzi z `IUnknown` interfejsu.

> [!IMPORTANT]
> Ta specjalizacja szablonu obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie. Zamiast tego użyj [IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) .

## <a name="syntax"></a>Składnia

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ argumentu *PP*.

*miesięcznie*<br/>
Wskaźnik pośrednika.

## <a name="return-value"></a>Wartość zwracana

Argument *PP* rzutowania na wskaźnik do elementu **`void`** .

## <a name="remarks"></a>Uwagi

Generowany jest błąd czasu kompilacji, jeśli parametr szablonu *T* nie pochodzi od `IUnknown` .

## <a name="requirements"></a>Wymagania

**Nagłówek:** Client. h
