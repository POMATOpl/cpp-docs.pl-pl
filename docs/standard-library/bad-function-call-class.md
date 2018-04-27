---
title: bad_function_call — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- functional/std::bad_function_call
dev_langs:
- C++
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9055729d02dd16fb66028bb2c3cbc4d70168e4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="badfunctioncall-class"></a>bad_function_call — Klasa

Raporty wywołanie funkcji uszkodzone.

## <a name="syntax"></a>Składnia

```cpp
class bad_function_call
 : public std::exception {
 };
```

## <a name="remarks"></a>Uwagi

Klasa opisuje wyjątek, aby wskazać, że wywołanie `operator()` na [funkcji klasy](../standard-library/function-class.md)
