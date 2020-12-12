---
description: 'Dowiedz się więcej na temat: stałe sterty'
title: Heap — Stałe
ms.date: 11/04/2016
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
ms.openlocfilehash: da90be1855f9a4714bc2d441651ac721ede84c1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120698"
---
# <a name="heap-constants"></a>Heap — Stałe

## <a name="syntax"></a>Składnia

```
#include <malloc.h>
```

## <a name="remarks"></a>Uwagi

Te stałe dają wartość zwracaną wskazującą stan sterty.

|Stała|Znaczenie|
|--------------|-------------|
|`_HEAPBADBEGIN`|Nie znaleziono informacji o nagłówku początkowym lub są one nieprawidłowe.|
|`_HEAPBADNODE`|Znaleziono zły węzeł lub sterta jest uszkodzona.|
|`_HEAPBADPTR`|pole **_pentry** struktury **_HEAPINFO** nie zawiera prawidłowego wskaźnika do sterty ( `_heapwalk` tylko procedura).|
|`_HEAPEMPTY`|Sterta nie została zainicjowana.|
|`_HEAPEND`|Koniec sterty został pomyślnie osiągnięty ( `_heapwalk` tylko procedura).|
|`_HEAPOK`|Sterta jest spójna ( `_heapset` `_heapchk` tylko procedura). Brak błędów do tej pory; Struktura **_HEAPINFO** zawiera informacje o następnym wpisie ( `_heapwalk` tylko procedura).|

## <a name="see-also"></a>Zobacz też

[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
