---
description: 'Dowiedz się więcej na temat: &lt; uwagi&gt;'
title: '&lt;uwagi> (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 0c919ba3101282fd755450489eacc6c0800fb437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225222"
---
# <a name="ltremarksgt"></a>&lt;uwagi&gt;

\<remarks>Tag służy do dodawania informacji o typie, uzupełniając informacje określone za pomocą [\<summary>](summary-visual-cpp.md) . Te informacje są wyświetlane w [Przeglądarka obiektów](/visualstudio/ide/viewing-the-structure-of-code) i w raporcie w sieci Web komentarza do kodu.

## <a name="syntax"></a>Składnia

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>Parametry

*zharmonizowan*<br/>
Opis elementu członkowskiego.

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

```cpp
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
