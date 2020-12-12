---
description: 'Dowiedz się więcej o: stałe uprawnień pliku'
title: Stałe uprawnień pliku
ms.date: 11/04/2016
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: a220ec404202b1f962a4c0bf51d20b7eea2720ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331078"
---
# <a name="file-permission-constants"></a>Stałe uprawnień pliku

## <a name="syntax"></a>Składnia

```
#include <sys/stat.h>
```

## <a name="remarks"></a>Uwagi

Jedna z tych stałych jest wymagana `_O_CREAT` , gdy ( `_open` , `_sopen` ) jest określony.

`pmode`Argument określa ustawienia uprawnień pliku w następujący sposób.

|Stała|Znaczenie|
|--------------|-------------|
|`_S_IREAD`|Odczytywanie dozwolone|
|`_S_IWRITE`|Dozwolone zapisywanie|
|`_S_IREAD` &#124; `_S_IWRITE`|Dozwolone odczytywanie i zapisywanie|

Gdy jest używany jako `pmode` argument dla `_umask` , stała manifestu ustawia ustawienie uprawnień w następujący sposób.

|Stała|Znaczenie|
|--------------|-------------|
|`_S_IREAD`|Zapisywanie nie jest dozwolone (plik jest tylko do odczytu)|
|`_S_IWRITE`|Odczytywanie jest niedozwolone (plik jest tylko do zapisu)|
|`_S_IREAD` &#124; `_S_IWRITE`|Nie ma uprawnień do odczytu ani zapisu|

## <a name="see-also"></a>Zobacz też

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[Typy standardowe](../c-runtime-library/standard-types.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
