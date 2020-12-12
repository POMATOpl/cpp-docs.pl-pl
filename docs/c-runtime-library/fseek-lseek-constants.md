---
description: 'Dowiedz się więcej o: fseek, _lseek stałych'
title: fseek, _lseek — Stałe
ms.date: 11/04/2016
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
ms.openlocfilehash: be12597682074f610b0a69395146b400fed4d6b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319820"
---
# <a name="fseek-_lseek-constants"></a>fseek, _lseek — Stałe

## <a name="syntax"></a>Składnia

```
#include <stdio.h>
```

## <a name="remarks"></a>Uwagi

Argument *Origin* określa początkową pozycję i może być jedną z następujących stałych manifestu:

|Stała|Znaczenie|
|--------------|-------------|
|`SEEK_END`|Koniec pliku|
|`SEEK_CUR`|Bieżąca pozycja wskaźnika pliku|
|`SEEK_SET`|Początek pliku|

## <a name="see-also"></a>Zobacz też

[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
