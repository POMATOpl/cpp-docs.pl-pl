---
description: 'Dowiedz się więcej na temat: &lt; c&gt;'
title: '&lt;c> (Komentarze dokumentacji języka C++)'
ms.date: 11/04/2016
f1_keywords:
- <c>
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
ms.openlocfilehash: 35d06183136a82c602b5e4daa288fb4518962154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182622"
---
# <a name="ltcgt"></a>&lt;s&gt;

\<c>Tag wskazuje, że tekst w opisie powinien być oznaczony jako kod. Użyj [\<code>](code-visual-cpp.md) , aby wskazać wiele wierszy jako kod.

## <a name="syntax"></a>Składnia

```
<c>text</c>
```

#### <a name="parameters"></a>Parametry

*tekst*<br/>
Tekst, który ma być wskazywany jako kod.

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

```cpp
// xml_c_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_c_tag.xdc

/// Text for class MyClass.
class MyClass {
public:
   int m_i;
   MyClass() : m_i(0) {}

   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.
   /// </summary>
   int MyMethod(MyClass * a) {
      return a -> m_i;
   }
};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
