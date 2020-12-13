---
description: Dowiedz się więcej na temat klasy parallel_policy
title: Klasa parallel_policy
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 1cead0bcc44256bf7d41d061d592849a7411b057
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340804"
---
# <a name="parallel_policy-class"></a>Klasa parallel_policy

Używany jako unikatowy typ niejednoznacznego przeciążenia algorytmu równoległego i wskazujący, że wykonywanie algorytmu równoległego może być równoległe.

## <a name="syntax"></a>Składnia

```cpp
class execution::parallel_policy;
```

## <a name="remarks"></a>Uwagi

W trakcie wykonywania algorytmu równoległego przy użyciu `execution::parallel_policy` zasad, jeśli wywołanie funkcji dostępu do elementu kończy się za pośrednictwem nieprzechwyconego wyjątku, należy `terminate()` wywołać.
