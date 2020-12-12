---
description: 'Dowiedz się więcej na temat: &lt; dołączanie&gt;'
title: '&lt;Uwzględnij> (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- <include>
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
ms.openlocfilehash: 577281b293fcca9b9b0b9491dd239240d435f32c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199782"
---
# <a name="ltincludegt"></a>&lt;include&gt;

\<include>Tag umożliwia odwoływanie się do komentarzy w innym pliku, które opisują typy i elementy członkowskie w kodzie źródłowym. Jest to alternatywa dla umieszczania komentarzy do dokumentacji bezpośrednio w pliku kodu źródłowego.  Na przykład, można użyć, \<include> Aby wstawić standardowe "typowe" Komentarze, które są używane przez zespół lub firmę.

## <a name="syntax"></a>Składnia

```
<include file='filename' path='tagpath' />
```

#### <a name="parameters"></a>Parametry

*Nazwa pliku*<br/>
Nazwa pliku zawierającego dokumentację. Nazwa pliku może być kwalifikowana za pomocą ścieżki.  Ujmij nazwę w pojedyncze lub podwójne cudzysłowy.  Kompilator generuje ostrzeżenie, jeśli nie znajdzie `filename` .

*tagpath*<br/>
Prawidłowe wyrażenie XPath, które wybiera żądany zestaw węzłów zawarty w pliku.

*Nazwij*<br/>
Specyfikator nazwy w tagu, który poprzedza Komentarze; `name` ma `id` .

*id*<br/>
Identyfikator tagu, który poprzedza Komentarze.  Ujmij nazwę w pojedyncze lub podwójne cudzysłowy.

## <a name="remarks"></a>Uwagi

\<include>Tag używa SKŁADNI XML XPath. Zapoznaj się z dokumentacją XPath, aby uzyskać informacje na temat sposobów dostosowywania za pomocą programu \<include> .

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

Jest to przykład wieloplikowy. Pierwszy plik, który używa \<include> , zawiera następujące komentarze dokumentacji:

```cpp
// xml_include_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_include_tag.dll

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />
public ref class Test {
   void TestMethod() {
   }
};

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />
public ref class Test2 {
   void Test() {
   }
};
```

Drugi plik, xml_include_tag.doc, zawiera następujące komentarze dokumentacji:

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>Dane wyjściowe programu

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>t2</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja XML](xml-documentation-visual-cpp.md)
