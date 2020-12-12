---
description: 'Dowiedz się więcej na temat: _WAIT_CHILD, _WAIT_GRANDCHILD'
title: _WAIT_CHILD, _WAIT_GRANDCHILD
ms.date: 11/04/2016
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
ms.openlocfilehash: b14586232258f635b428b6c197213782591c8af1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181660"
---
# <a name="_wait_child-_wait_grandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD

## <a name="syntax"></a>Składnia

```
#include <process.h>
```

## <a name="remarks"></a>Uwagi

`_cwait`Funkcja może być używana przez każdy proces do oczekiwania na inny proces (jeśli znany jest identyfikator procesu). Argument akcji może być jedną z następujących wartości:

|Stała|Znaczenie|
|--------------|-------------|
|`_WAIT_CHILD`|Proces wywołujący czeka na zakończenie określonego nowego procesu.|
|`_WAIT_GRANDCHILD`|Proces wywołujący oczekuje do określonego nowego procesu i wszystkich procesów utworzonych przez ten nowy proces zakończy się.|

## <a name="see-also"></a>Zobacz też

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
