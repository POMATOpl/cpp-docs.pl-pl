---
description: 'Dowiedz się więcej na temat: &lt; Podsumowanie&gt;'
title: '&lt;Podsumowanie> (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 73e36367ff1a36f2b030525ea22f634ae74b64a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230227"
---
# <a name="ltsummarygt"></a>&lt;Podsumowanie&gt;

\<summary>Tag powinien służyć do opisywania typu lub elementu członkowskiego typu. Służy [\<remarks>](remarks-visual-cpp.md) do dodawania dodatkowych informacji do opisu typu.

## <a name="syntax"></a>Składnia

```
<summary>description</summary>
```

#### <a name="parameters"></a>Parametry

*zharmonizowan*<br/>
Podsumowanie obiektu.

## <a name="remarks"></a>Uwagi

Tekst \<summary> znacznika jest jedynym źródłem informacji o typie w IntelliSense i jest również wyświetlany w [Przeglądarka obiektów](/visualstudio/ide/viewing-the-structure-of-code) i w raporcie w sieci Web komentarza do kodu.

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

```cpp
// xml_summary_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_summary_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>MyMethod is a method in the MyClass class.
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>
   /// <seealso cref="MyClass::MyMethod2"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void MyMethod2() {}
};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
