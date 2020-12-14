---
description: Dowiedz się więcej na temat klasy sequenced_policy
title: Klasa sequenced_policy
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: e4d19e3649e3c768e8efc062baaf735e28a8fc22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250416"
---
# <a name="sequenced_policy-class"></a>Klasa sequenced_policy

Używany jako unikatowy typ odróżnienia przeciążenia algorytmu równoległego i wymaganie, aby wykonywanie algorytmu równoległego mogło nie być równoległe.

## <a name="syntax"></a>Składnia

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>Uwagi

W trakcie wykonywania algorytmu równoległego przy użyciu `execution::sequenced_policy` zasad, jeśli wywołanie funkcji dostępu do elementu kończy się za pośrednictwem nieprzechwyconego wyjątku, należy `terminate()` wywołać.
