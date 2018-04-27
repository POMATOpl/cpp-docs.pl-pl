---
title: '&lt;system_error —&gt; definicje typów | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 701df57adb0576160f5aade9fd26220c852150ac
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="ltsystemerrorgt-typedefs"></a>&lt;system_error —&gt; definicje typów

||
|-|
|[generic_errno](#generic_errno)|

## <a name="generic_errno"></a>  generic_errno

Typ reprezentujący wyliczenia, którego zawiera nazwy symbolicznej dla makra kod błędu zdefiniowany przez Posix w `<errno.h>`.

```cpp
typedef errc generic_error;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem [errc —](../standard-library/system-error-enums.md#errc).

## <a name="see-also"></a>Zobacz także

[<system_error>](../standard-library/system-error.md)<br/>
