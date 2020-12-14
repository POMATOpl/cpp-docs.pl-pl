---
description: 'Dowiedz się więcej na temat: &lt; wartość&gt;'
title: '&lt;> wartości (Komentarze w dokumentacji C++)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: 110091607af7c973591384d44816f372f0d15b14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187030"
---
# <a name="ltvaluegt"></a>&lt;value&gt;

\<value>Tag pozwala opisać metody akcesora właściwości i właściwości. Należy pamiętać, że po dodaniu właściwości z kreatorem kodu w zintegrowanym środowisku programistycznym programu Visual Studio zostanie dodany [\<summary>](summary-visual-cpp.md) tag nowej właściwości. Następnie należy ręcznie dodać tag, \<value> aby opisać wartość, którą reprezentuje właściwość.

## <a name="syntax"></a>Składnia

```
<value>property-description</value>
```

#### <a name="parameters"></a>Parametry

*Opis właściwości*<br/>
Opis właściwości.

## <a name="remarks"></a>Uwagi

Kompiluj z [/doc](doc-process-documentation-comments-c-cpp.md) , aby przetwarzać komentarze dokumentacji do pliku.

## <a name="example"></a>Przykład

```cpp
// xml_value_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_value_tag.dll
using namespace System;
/// Text for class Employee.
public ref class Employee {
private:
   String ^ name;
   /// <value>Name accesses the value of the name data member</value>
public:
   property String ^ Name {
      String ^ get() {
         return name;
      }
      void set(String ^ i) {
         name = i;
      }
   }
};
```

## <a name="see-also"></a>Zobacz także

[Dokumentacja XML](xml-documentation-visual-cpp.md)
