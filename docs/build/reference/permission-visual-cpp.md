---
description: 'Dowiedz się więcej na temat: &lt; uprawnienie&gt;'
title: '&lt;> uprawnień (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: cd815b5df831632afd399e752e4525082f20b063
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226028"
---
# <a name="ltpermissiongt"></a>&lt;zezwolenie&gt;

\<permission>Tag umożliwia dokumentowanie dostępu do elementu członkowskiego. <xref:System.Security.PermissionSet> pozwala określić dostęp do elementu członkowskiego.

## <a name="syntax"></a>Składnia

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>Parametry

*członkiem*<br/>
Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji. Kompilator sprawdza, czy dany element kodu istnieje i tłumaczy `member` na nazwę elementu kanonicznego w wyjściowym kodzie XML.  Ujmij nazwę w pojedyncze lub podwójne cudzysłowy.

Kompilator generuje ostrzeżenie, jeśli nie znajdzie `member` .

Aby uzyskać informacje na temat sposobu tworzenia odwołania cref do typu ogólnego, zobacz [\<see>](see-visual-cpp.md) .

*zharmonizowan*<br/>
Opis dostępu do elementu członkowskiego.

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

Kompilator MSVC podejmie próbę rozpoznania odwołań cref w jednym przejściu poprzez Komentarze do dokumentacji.  W związku z tym, w przypadku używania reguł wyszukiwania C++ symbol nie zostanie znaleziony przez kompilator, odwołanie zostanie oznaczone jako nierozwiązane. [\<seealso>](seealso-visual-cpp.md)Aby uzyskać więcej informacji, zobacz.

## <a name="example"></a>Przykład

```cpp
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
