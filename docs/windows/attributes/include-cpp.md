---
description: 'Dowiedz się więcej o: include (C++)'
title: include (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: c6d12b9d8826ce84de0c01aaf055f5a4176fea10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321366"
---
# <a name="include-c"></a>include (C++)

Określa co najmniej jeden plik nagłówka do uwzględnienia w wygenerowanym pliku IDL.

## <a name="syntax"></a>Składnia

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Parametry

*header_file*<br/>
Nazwa pliku, który ma zostać uwzględniony w wygenerowanym pliku IDL.

## <a name="remarks"></a>Uwagi

Atrybut **include** C++ powoduje `#include` umieszczenie instrukcji poniżej `import "docobj.idl"` instrukcji w wygenerowanym pliku IDL.

Atrybut **include** języka C++ ma takie same funkcje jak atrybut [include](/windows/win32/Midl/include) MIDL.

## <a name="example"></a>Przykład

Poniższy kod przedstawia przykład użycia metody **include**. W tym przykładzie plik zawiera. h zawiera tylko `#include` instrukcję.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Dowolne miejsce|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty autonomiczne](stand-alone-attributes.md)<br/>
[zaimportować](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib —](includelib-cpp.md)<br/>
[importlib](importlib.md)
