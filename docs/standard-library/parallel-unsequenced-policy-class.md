---
description: Dowiedz się więcej na temat klasy parallel_unsequenced_policy
title: Klasa parallel_unsequenced_policy
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_unsequenced_policy
ms.openlocfilehash: e39edc0979bf1374bc6092dbadb032811180f668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340791"
---
# <a name="parallel_unsequenced_policy-class"></a>Klasa parallel_unsequenced_policy

Używany jako unikatowy typ niejednoznacznego przeciążenia algorytmu równoległego i wskazujący, że wykonywanie algorytmu równoległego może być równoległe i wektorowe.

## <a name="syntax"></a>Składnia

```cpp
class execution::parallel_unsequenced_policy;
```

## <a name="remarks"></a>Uwagi

W trakcie wykonywania algorytmu równoległego przy użyciu `execution::parallel_unsequenced_policy` zasad, jeśli wywołanie funkcji dostępu do elementu kończy się za pośrednictwem nieprzechwyconego wyjątku, należy `terminate()` wywołać.
