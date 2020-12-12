---
description: 'Dowiedz się więcej na temat: embedded_idl Importowanie atrybutu'
title: embedded_idl atrybut importowania
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: a56c6e664c082db4b6eac078b7133a1ead947d3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300596"
---
# <a name="embedded_idl-import-attribute"></a>embedded_idl atrybut importowania

**Specyficzne dla języka C++**

Określa, czy biblioteka typów jest zapisywana w `.tlh` pliku z zachowaniem kodu generowanego przez atrybut.

## <a name="syntax"></a>Składnia

> **#import** **embedded_idl** *biblioteki typów* [ **(** { **"emitidl"**  |  **"no_emitidl"** } **)** ]

### <a name="parameters"></a>Parametry

**emitidl**\
Informacje o typie zaimportowane z *biblioteki typów* są obecne w IDL wygenerowanym dla projektu o atrybutach. To zachowanie jest domyślne i obowiązuje, jeśli nie określisz parametru do `embedded_idl` .

**"no_emitidl"**\
Informacje o typie zaimportowane z *biblioteki typów* nie są obecne w IDL wygenerowanym dla projektu o atrybutach.

## <a name="example"></a>Przykład

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**ZAKOŃCZENIE specyficzne dla języka C++**

## <a name="see-also"></a>Zobacz też

[Atrybuty #import](../preprocessor/hash-import-attributes-cpp.md)\
[#import — dyrektywa](../preprocessor/hash-import-directive-cpp.md)
