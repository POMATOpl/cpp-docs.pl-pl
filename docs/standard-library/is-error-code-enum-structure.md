---
title: is_error_code_enum — struktura | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::is_error_code_enum
dev_langs:
- C++
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d28754bd005627fc6c14d5d8870941158bff937
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843343"
---
# <a name="iserrorcodeenum-structure"></a>is_error_code_enum — Struktura

Specjalizacja, która wskazuje, że [future_errc —](../standard-library/future-enums.md#future_errc) nadaje się do przechowywania [error_code —](../standard-library/error-code-class.md).

## <a name="syntax"></a>Składnia

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<przyszłych >

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[Odwołanie do plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
