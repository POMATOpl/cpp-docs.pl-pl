---
description: Dowiedz się więcej na temat struktury high_resolution_clock
title: Struktura high_resolution_clock | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology: cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::high_resolution_clock
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c5272413636e40dadf9201f684d32aaaa6708ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324057"
---
# <a name="high_resolution_clock-struct"></a>Struktura high_resolution_clock

Przedstawia zegar *high_resolution* .

## <a name="syntax"></a>Składnia

```cpp
class high_resolution_clock
```

## <a name="members"></a>Elementy członkowskie

### <a name="typedefs"></a>Typedefs

|Nazwa|Opis|
|----------|-----------------|
|`duration`|Synonim dla `nanoseconds` , zdefiniowany w \<chrono> .|
|`period`|Synonim dla `nano` , zdefiniowany w \<ratio> .|
|`rep`|Synonim dla **`long long`** typu, który jest używany do reprezentowania liczby taktów zegara w zawartym utworzeniu wystąpienia `duration` .|
|`time_point`|Synonim dla `chrono::time_point<high_resolution_clock>` .|

## <a name="functions"></a>Funkcje

|Nazwa|Opis|
|-|-|
|`now`|Zwraca bieżący czas jako `time_point` wartość.|

## <a name="constants"></a>Stałe

|Nazwa|Opis|
|----------|-----------------|
|`is_steady`|Zawiera **`true`** . `high_resolution_clock`Jest *stała*.|
