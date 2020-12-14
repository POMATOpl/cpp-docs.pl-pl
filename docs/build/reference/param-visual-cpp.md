---
description: 'Dowiedz się więcej na temat: &lt; param&gt;'
title: '&lt;param> (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: 7c3baabc6aef9a4cabdd7c7a9023fb628bd53793
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226145"
---
# <a name="ltparamgt"></a>&lt;param&gt;

\<param>Tag powinien być używany w komentarzu dla deklaracji metody, aby opisać jeden z parametrów dla metody.

## <a name="syntax"></a>Składnia

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>Parametry

*Nazwij*<br/>
Nazwa parametru metody.  Ujmij nazwę w pojedyncze lub podwójne cudzysłowy.  Kompilator generuje ostrzeżenie, jeśli nie znajdzie `name` .

*zharmonizowan*<br/>
Opis parametru.

## <a name="remarks"></a>Uwagi

Tekst dla \<param> tagu będzie wyświetlany w technologii IntelliSense, [Przeglądarka obiektów](/visualstudio/ide/viewing-the-structure-of-code)i w raporcie w sieci Web komentarza do kodu.

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

```cpp
// xml_param_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_param_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <param name="Int1">Used to indicate status.</param>
   void MyMethod(int Int1) {
   }
};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
