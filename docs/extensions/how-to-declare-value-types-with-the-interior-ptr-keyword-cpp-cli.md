---
description: 'Dowiedz się więcej na temat: Instrukcje: deklarowanie typów wartości za pomocą słowa kluczowego interior_ptr (C++/CLI)'
title: 'Poradnik: Deklarowanie typów wartości za pomocą słowa kluczowego interior_ptr (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: b8d5c554f212a9536b0ad063d67e044c08194015
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119177"
---
# <a name="how-to-declare-value-types-with-the-interior_ptr-keyword-ccli"></a>Poradnik: Deklarowanie typów wartości za pomocą słowa kluczowego interior_ptr (C++/CLI)

**Interior_ptr** może być używana z typem wartości.

> [!IMPORTANT]
> Ta funkcja języka jest obsługiwana przez `/clr` opcję kompilatora, ale nie przez `/ZW` opcję kompilatora.

## <a name="example-interior_ptr-with-value-type"></a>Przykład: interior_ptr z typem wartości

### <a name="description"></a>Opis

Poniższy przykład C++/CLI pokazuje, jak używać **interior_ptr** z typem wartości.

### <a name="code"></a>Kod

```cpp
// interior_ptr_value_types.cpp
// compile with: /clr
value struct V {
   V(int i) : data(i){}
   int data;
};

int main() {
   V v(1);
   System::Console::WriteLine(v.data);

   // pointing to a value type
   interior_ptr<V> pv = &v;
   pv->data = 2;

   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);

   // pointing into a value type
   interior_ptr<int> pi = &v.data;
   *pi = 3;
   System::Console::WriteLine(*pi);
   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);
}
```

```Output
1
2
2
3
3
3
```

## <a name="example-this-pointer"></a>Przykład: ten wskaźnik

### <a name="description"></a>Opis

W typie wartości **`this`** wskaźnik szacuje się interior_ptr.

W treści niestatycznej funkcji składowej typu wartości `V` , **`this`** jest wyrażeniem typu, `interior_ptr<V>` którego wartość jest adresem obiektu, dla którego wywoływana jest funkcja.

### <a name="code"></a>Kod

```cpp
// interior_ptr_value_types_this.cpp
// compile with: /clr /LD
value struct V {
   int data;
   void f() {
      interior_ptr<V> pv1 = this;
      // V* pv2 = this;   error
   }
};
```

## <a name="example-address-of-operator"></a>Przykład: operator address-of

### <a name="description"></a>Opis

Poniższy przykład pokazuje, jak używać operatora address-of ze statycznymi składowymi.

Adres elementu członkowskiego typu statycznego Visual C++ zwraca wskaźnik natywny.  Adres elementu członkowskiego typu wartości statycznej jest wskaźnikiem zarządzanym, ponieważ element członkowski typu wartości jest przypisywany na stercie środowiska uruchomieniowego i może być przenoszony przez moduł zbierający elementy bezużyteczne.

### <a name="code"></a>Kod

```cpp
// interior_ptr_value_static.cpp
// compile with: /clr
using namespace System;
value struct V { int i; };

ref struct G {
   static V v = {22};
   static int i = 23;
   static String^ pS = "hello";
};

int main() {
   interior_ptr<int> p1 = &G::v.i;
   Console::WriteLine(*p1);

   interior_ptr<int> p2 = &G::i;
   Console::WriteLine(*p2);

   interior_ptr<String^> p3 = &G::pS;
   Console::WriteLine(*p3);
}
```

```Output
22
23
hello
```

## <a name="see-also"></a>Zobacz też

[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)
