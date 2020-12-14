---
description: 'Dowiedz się więcej na temat: &lt; seealso —&gt;'
title: '&lt;seealso —> (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- <seealso>
- seealso
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
ms.openlocfilehash: 70f5f0147ff56dd6327e99f073f80c28a7cce539
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224728"
---
# <a name="ltseealsogt"></a>&lt;seealso —&gt;

\<seealso>Tag pozwala określić tekst, który może być wyświetlany w sekcji Zobacz też. Służy [\<see>](see-visual-cpp.md) do określania linku w tekście.

## <a name="syntax"></a>Składnia

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>Parametry

*członkiem*<br/>
Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji.  Ujmij nazwę w pojedyncze lub podwójne cudzysłowy.

Kompilator sprawdza, czy dany element kodu istnieje i jest rozpoznawany jako `member` Nazwa elementu w wyjściowym kodzie XML.  Kompilator generuje ostrzeżenie, jeśli nie znajdzie `member` .

Aby uzyskać informacje na temat sposobu tworzenia odwołania cref do typu ogólnego, zobacz [\<see>](see-visual-cpp.md) .

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

Zobacz [\<summary>](summary-visual-cpp.md) , aby zobaczyć przykład użycia \<seealso> .

Kompilator MSVC podejmie próbę rozpoznania odwołań cref w jednym przejściu poprzez Komentarze do dokumentacji.  W związku z tym, w przypadku używania reguł wyszukiwania C++ symbol nie zostanie znaleziony przez kompilator, odwołanie zostanie oznaczone jako nierozwiązane.

## <a name="example"></a>Przykład

W poniższym przykładzie odwołuje się do nierozpoznanego symbolu w cref. Komentarz XML dla cref do B:: test będzie `<seealso cref="!:B::Test" />` , podczas gdy odwołanie do:: test jest poprawnie sformułowane `<seealso cref="M:A.Test" />` .

```cpp
// xml_seealso_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_seealso_tag.dll

/// Text for class A.
public ref struct A {
   /// <summary><seealso cref="A::Test"/>
   /// <seealso cref="B::Test"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void Test() {}
};

/// Text for class B.
public ref struct B {
   void Test() {}
};
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja XML](xml-documentation-visual-cpp.md)
