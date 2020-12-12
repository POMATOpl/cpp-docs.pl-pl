---
description: 'Dowiedz się więcej na temat: &lt; Zobacz&gt;'
title: '&lt;Zobacz> (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: b4f8f9a2312a3db1ce2840209668b7b23837ab31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224741"
---
# <a name="ltseegt"></a>&lt;wyświetlania&gt;

\<see>Tag pozwala określić łącze z poziomu tekstu. Użyj, [\<seealso>](seealso-visual-cpp.md) Aby wskazać tekst, który może być wyświetlany w sekcji Zobacz też.

## <a name="syntax"></a>Składnia

```
<see cref="member"/>
```

#### <a name="parameters"></a>Parametry

*członkiem*<br/>
Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji.  Ujmij nazwę w pojedyncze lub podwójne cudzysłowy.

Kompilator sprawdza, czy dany element kodu istnieje i jest rozpoznawany jako `member` Nazwa elementu w wyjściowym kodzie XML.  Kompilator generuje ostrzeżenie, jeśli nie znajdzie `member` .

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

Zobacz [\<summary>](summary-visual-cpp.md) , aby zobaczyć przykład użycia \<see> .

Kompilator MSVC podejmie próbę rozpoznania odwołań cref w jednym przejściu poprzez Komentarze do dokumentacji.  W związku z tym, w przypadku używania reguł wyszukiwania C++ symbol nie zostanie znaleziony przez kompilator, odwołanie zostanie oznaczone jako nierozwiązane. [\<seealso>](seealso-visual-cpp.md)Aby uzyskać więcej informacji, zobacz.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak można utworzyć odwołanie cref do typu ogólnego, takiego jak kompilator rozpozna odwołanie.

```cpp
// xml_see_cref_example.cpp
// compile with: /LD /clr /doc
// the following cref shows how to specify the reference, such that,
// the compiler will resolve the reference
/// <see cref="C{T}">
/// </see>
ref class A {};

// the following cref shows another way to specify the reference,
// such that, the compiler will resolve the reference
/// <see cref="C < T >"/>

// the following cref shows how to hard-code the reference
/// <see cref="T:C`1">
/// </see>
ref class B {};

/// <see cref="A">
/// </see>
/// <typeparam name="T"></typeparam>
generic<class T>
ref class C {};
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja XML](xml-documentation-visual-cpp.md)
