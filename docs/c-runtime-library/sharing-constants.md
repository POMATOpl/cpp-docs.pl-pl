---
description: 'Dowiedz się więcej na temat: udostępnianie stałych'
title: Udostępnianie stałych
ms.date: 11/04/2016
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
ms.openlocfilehash: 7cda55d16a9b59c30e9fdbce47c565552839e792
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176174"
---
# <a name="sharing-constants"></a>Udostępnianie stałych

Stałe dla trybów udostępniania plików.

## <a name="syntax"></a>Składnia

```
#include <share.h>
```

## <a name="remarks"></a>Uwagi

Argument *Shflag* określa tryb udostępniania, który składa się z co najmniej jednej stałej manifestu. Można je łączyć z argumentami *Oflag* (zobacz [stałe plików](../c-runtime-library/file-constants.md)).

W poniższej tabeli wymieniono stałe i ich znaczenie:

|Stała|Znaczenie|
|--------------|-------------|
|`_SH_DENYRW`|Nie zezwala na dostęp do odczytu i zapisu do pliku|
|`_SH_DENYWR`|Odmawia dostępu do zapisu do pliku|
|`_SH_DENYRD`|Nie zezwala na dostęp do odczytu do pliku|
|`_SH_DENYNO`|Zezwala na dostęp do odczytu i zapisu|
|`_SH_SECURE`|Ustawia tryb bezpieczny (odczyt współużytkowany, wyłączny dostęp do zapisu).|

## <a name="see-also"></a>Zobacz też

[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
