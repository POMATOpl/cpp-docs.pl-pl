---
title: emitidl (atrybut C++ COM) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e11e1ce061fcf2e9ce21155dcbeb93b45b66238
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789730"
---
# <a name="emitidl"></a>emitidl

Określa, czy wszystkie kolejne atrybuty IDL są przetwarzane i umieszczane w pliku .idl wygenerowany.

## <a name="syntax"></a>Składnia

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>Parametry

*state*<br/>
Jedną z następujących wartości: `true`, `false`, `forced`, `restricted`, `push`, lub `pop`.

- Jeśli `true`, wszelkie atrybuty kategorii IDL w pliku kodu źródłowego są umieszczane w pliku .idl wygenerowany. Jest to domyślne ustawienie dla **emitidl**.

- Jeśli `false`, wszelkie atrybuty kategorii IDL w pliku kodu źródłowego nie będą wprowadzone w pliku .idl wygenerowany.

- Jeśli `restricted`, umożliwia atrybuty IDL, znajdować się w pliku bez [modułu](module-cpp.md) atrybutu. Kompilator nie generuje pliku .idl.

- Jeśli `forced`, zastępuje kolejnej `restricted` atrybut, który wymaga pliku, aby zawierała `module` atrybut, jeśli istnieją IDL atrybutów w pliku.

- `push` Umożliwia zapisanie bieżącego **emitidl** ustawienia do wewnętrznego **emitidl** stosu, i `pop` pozwala ustawić **emitidl** na dowolną wartość znajduje się na górze wewnętrznego **emitidl** stosu.

`defaultimports=`*wartość logiczna* \(opcjonalne)  
- Jeśli *logiczna* jest **true**, docobj.idl są importowane do pliku .idl wygenerowany. Ponadto jeśli plik o takiej samej nazwie jak .h pliku .idl, który `#include` do Twojego źródła kod znajduje się w tym samym katalogu co plik .h, a następnie pliku .idl wygenerowanego zawiera instrukcję import dla tego pliku .idl.

- Jeśli *logiczna* jest **false**, docobj.idl nie jest zaimportowany do pliku .idl wygenerowany. Należy jawnie zaimportować .IDL — pliki za pomocą [zaimportować](import.md).

## <a name="remarks"></a>Uwagi

Po **emitidl** atrybut C++ występuje w pliku kodu źródłowego, IDL atrybuty kategorii są umieszczane w pliku .idl wygenerowany. W przypadku nie **emitidl** atrybutu, atrybuty IDL w pliku kodu źródłowego są dane wyjściowe do pliku .idl wygenerowany.

Użytkownik może mieć wielu **emitidl** atrybutów w pliku kodu źródłowego. Jeśli `[emitidl(false)];` występuje w pliku bez dalszej `[emitidl(true)];`, a następnie atrybuty nie są przetwarzane w pliku .idl wygenerowany.

Każdorazowo, kompilator napotka nowy plik **emitidl** niejawnie ustawiono **true**.

## <a name="requirements"></a>Wymagania

### <a name="attribute-context"></a>Kontekst atrybutu

|||
|-|-|
|**Dotyczy**|Dowolne miejsce|
|**Powtarzalne**|Nie|
|**Wymaganych atrybutów**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutu](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty kompilatora](compiler-attributes.md)<br/>
[Oddzielne atrybuty](stand-alone-attributes.md)  