---
description: 'Dowiedz się więcej na temat: _CRT_DISABLE_PERFCRIT_LOCKS'
title: _CRT_DISABLE_PERFCRIT_LOCKS
ms.date: 11/04/2016
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
ms.openlocfilehash: b96e29fad635ac9e7f3d622ace3c43bb26c8805a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195687"
---
# <a name="_crt_disable_perfcrit_locks"></a>_CRT_DISABLE_PERFCRIT_LOCKS

Wyłącza blokowanie krytyczne dla wydajności w operacjach we/wy.

## <a name="syntax"></a>Składnia

```
#define _CRT_DISABLE_PERFCRIT_LOCKS
```

## <a name="remarks"></a>Uwagi

Zdefiniowanie tego symbolu może zwiększyć wydajność w przypadku programów z ograniczeniami we/wy, wymuszając wszystkie operacje we/wy, aby założyć jeden wielowątkowy model we/wy. Aby uzyskać więcej informacji, zobacz temat [wydajność bibliotek wielowątkowych](../c-runtime-library/multithreaded-libraries-performance.md).

## <a name="see-also"></a>Zobacz też

[Stałe globalne](../c-runtime-library/global-constants.md)
