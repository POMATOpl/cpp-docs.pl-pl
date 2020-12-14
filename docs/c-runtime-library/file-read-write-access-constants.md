---
description: 'Dowiedz się więcej na temat: stałe dostępu do odczytu/zapisu plików'
title: Stałe dostępu do pliku Read-Write
ms.date: 11/04/2016
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
ms.openlocfilehash: 3c1fe6f6125b52f24b35a03c4c517385410f1fae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224260"
---
# <a name="file-readwrite-access-constants"></a>Odczyt/zapis pliku — Stałe dostępu

## <a name="syntax"></a>Składnia

```
#include <stdio.h>
```

## <a name="remarks"></a>Uwagi

Te stałe określają typ dostępu ("a", "r" lub "w") żądany dla tego pliku. Zarówno [tryb tłumaczenia](../c-runtime-library/file-translation-constants.md) ("b", "t"), jak i [tryb zatwierdzania na dysku](../c-runtime-library/commit-to-disk-constants.md) ("c" lub "n") można określić przy użyciu typu dostępu.

Typy dostępu zostały opisane w tej tabeli:

|Typ dostępu|Opis|
|----------|----------------|
|**®**|Otwiera do odczytu. Jeśli plik nie istnieje lub nie można go znaleźć, wywołanie otwarcia pliku kończy się niepowodzeniem.|
|**k**|Otwiera pusty plik do zapisu. Jeśli dany plik istnieje, jego zawartość zostaje zniszczona.|
|**z**|Otwiera do zapisu na końcu pliku (dołączanie); najpierw tworzy plik, jeśli nie istnieje. Wszystkie operacje zapisu odbywają się na końcu pliku. Mimo że można zmienić położenie wskaźnika pliku przy użyciu `fseek` lub `rewind` , jest on zawsze przenoszony z powrotem do końca pliku przed przeprowadzeniem jakiejkolwiek operacji zapisu. |
|**"r +"**|Otwiera zarówno do odczytu, jak i do zapisu. Jeśli plik nie istnieje lub nie można go znaleźć, wywołanie otwarcia pliku kończy się niepowodzeniem.|
|**"w +"**|Otwiera pusty plik do odczytu i zapisu. Jeśli dany plik istnieje, jego zawartość zostaje zniszczona.|
|**"a +"**|Taka sama jak **"a"** , ale również umożliwia odczytywanie.|

W przypadku określenia typu "r +", "z +" lub "a +" są dozwolone operacje odczytu i zapisu (plik zostanie otwarty dla "Update"). Jednak podczas przełączania się między operacjami odczytu i zapisu musi istnieć interwencja `fflush` , `fsetpos` , `fseek` lub `rewind` operacja. Bieżącą pozycję można określić dla `fsetpos` `fseek` operacji lub.

## <a name="see-also"></a>Zobacz też

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
