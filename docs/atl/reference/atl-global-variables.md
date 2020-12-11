---
description: 'Dowiedz się więcej o: zmienne globalne ATL'
title: Zmienne globalne ATL
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 8d0544651e32f5e569973466af8ce04af1433766
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158780"
---
# <a name="atl-global-variables"></a>Zmienne globalne ATL

## <a name="_patlmodule"></a>_pAtlModule

Zmienna globalna przechowująca wskaźnik do bieżącego modułu.

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>Uwagi

Metody tej zmiennej globalnej mogą służyć do udostępnienia funkcji CComModule (obecnie przestarzałe) klasy w Visual C++ 6,0.

### <a name="example"></a>Przykład

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h
