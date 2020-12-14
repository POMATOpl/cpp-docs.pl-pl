---
description: 'Dowiedz się więcej o: &lt; przykład&gt;'
title: '&lt;przykład> (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: 8ffa51be888fb631db6ec1ecd145177ea346084f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200835"
---
# <a name="ltexamplegt"></a>&lt;przyklad&gt;

\<example>Tag pozwala określić przykład użycia metody lub innego elementu członkowskiego biblioteki. Często dotyczy to również użycia [\<code>](code-visual-cpp.md) znacznika.

## <a name="syntax"></a>Składnia

```
<example>description</example>
```

#### <a name="parameters"></a>Parametry

*zharmonizowan*<br/>
Opis przykładu kodu.

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

```cpp
// xml_example_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_example_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>
   /// GetZero method
   /// </summary>
   /// <example> This sample shows how to call the GetZero method.
   /// <code>
   /// int main()
   /// {
   ///    return GetZero();
   /// }
   /// </code>
   /// </example>
   static int GetZero() {
      return 0;
   }
};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
