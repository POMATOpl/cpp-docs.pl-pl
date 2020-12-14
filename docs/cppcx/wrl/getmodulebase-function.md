---
description: 'Dowiedz się więcej na temat: funkcja GetModuleBase'
title: GetModuleBase — Funkcja
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: cdedaf905da194400209840b6bd84fa8e626eb0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295201"
---
# <a name="getmodulebase-function"></a>GetModuleBase, funkcja

Pobiera wskaźnik [ModuleBase](modulebase-class.md) , który pozwala na zwiększanie i zmniejszanie liczby odwołań obiektu [RuntimeClass](runtimeclass-class.md) .

## <a name="syntax"></a>Składnia

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do `ModuleBase` obiektu.

## <a name="remarks"></a>Uwagi

Ta funkcja jest używana wewnętrznie do zwiększania i zmniejszania liczby odwołań do obiektów.

Za pomocą tej funkcji można kontrolować liczby odwołań przez wywołanie [ModuleBase:: IncrementObjectCount —](modulebase-class.md#incrementobjectcount) i [ModuleBase::D ecrementobjectcount](modulebase-class.md#decrementobjectcount).

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
