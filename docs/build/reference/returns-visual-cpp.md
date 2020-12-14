---
description: 'Dowiedz się więcej na temat: &lt; zwraca&gt;'
title: '&lt;zwraca> (Komentarze dokumentacji języka C++)'
ms.date: 11/04/2016
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
ms.openlocfilehash: c07439610fa0259a38a4c1993ead7f0f06023e5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225053"
---
# <a name="ltreturnsgt"></a>&lt;typu&gt;

\<returns>Tag powinien być używany w komentarzu dla deklaracji metody, aby opisać wartość zwracaną.

## <a name="syntax"></a>Składnia

```
<returns>description</returns>
```

#### <a name="parameters"></a>Parametry

*zharmonizowan*<br/>
Opis wartości zwracanej.

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

```cpp
// xml_returns_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_returns_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <returns>Returns zero.</returns>
   int GetZero() { return 0; }
};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
