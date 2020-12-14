---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4325'
title: Ostrzeżenie kompilatora (poziom 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 17e14d4909e4b76d6a0a71d6e77fad1d01e3f41b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311594"
---
# <a name="compiler-warning-level-1-c4325"></a>Ostrzeżenie kompilatora (poziom 1) C4325

> atrybuty dla sekcji standardowej "*Section*" zostały zignorowane

## <a name="remarks"></a>Uwagi

Nie można zmienić atrybutów sekcji standardowa. Na przykład:

```cpp
#pragma section(".sdata", long)
```

Spowoduje to zastąpienie `.sdata` standardowej sekcji, która używa **`short`** typu danych z **`long`** typem danych.

Standardowe sekcje, których atrybuty nie mogą ulec zmianie,

- . dane

- . sdata

- . BSS

- . sbss

- . Text

- . const

- .sconst

- . RDATA

- .srdata

Dodatkowe sekcje można dodać później.

## <a name="see-also"></a>Zobacz też

[Paragraf](../../preprocessor/section.md)
