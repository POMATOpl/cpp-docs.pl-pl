---
description: Dowiedz się więcej na temat struktury _stat st_mode stałych pól
title: Stałe pola_stat Struktura st_mode
ms.date: 11/04/2016
f1_keywords:
- S_IFCHR
- S_IFDIR
- _S_IWRITE
- S_IFMT
- _S_IFDIR
- _S_IREAD
- S_IEXEC
- _S_IEXEC
- _S_IFMT
- S_IWRITE
- S_IFREG
- S_IREAD
- _S_IFCHR
- _S_IFREG
helpviewer_keywords:
- S_IFDIR constant
- stat structure
- S_IWRITE constant
- S_IEXEC constant
- _S_IFREG constant
- S_IREAD constant
- stat structure, constants
- _S_IFMT constant
- st_mode field constants
- S_IFMT constant
- _S_IEXEC constant
- _S_IWRITE constant
- _S_IFDIR constant
- S_IFREG constant
- S_IFCHR constant
- _S_IREAD constant
- _S_IFCHR constant
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
ms.openlocfilehash: bd304119c705196981342caf5a257cc113fed923
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235739"
---
# <a name="_stat-structure-st_mode-field-constants"></a>Stałe pola_stat Struktura st_mode

## <a name="syntax"></a>Składnia

```
#include <sys/stat.h>
```

## <a name="remarks"></a>Uwagi

Te stałe są używane do wskazywania typu pliku w polu **st_mode** [struktury _stat](../c-runtime-library/standard-types.md).

Stałe maski bitowe są opisane poniżej:

|Stała|Znaczenie|
|--------------|-------------|
|`_S_IFMT`|Maska typu pliku|
|`_S_IFDIR`|Katalog|
|`_S_IFCHR`|Znak specjalny (wskazuje urządzenie, jeśli zostało ustawione)|
|`_S_IFREG`|Zwykły|
|`_S_IREAD`|Uprawnienie Odczyt, właściciel|
|`_S_IWRITE`|Uprawnienie do zapisu, właściciel|
|`_S_IEXEC`|Uprawnienie wykonaj/Wyszukaj, właściciel|

## <a name="see-also"></a>Zobacz też

[_stat, funkcje _wstat](../c-runtime-library/reference/stat-functions.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[Typy standardowe](../c-runtime-library/standard-types.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
