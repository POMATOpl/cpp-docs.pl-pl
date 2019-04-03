---
title: Przesłoń (C + +/ CLI i C + +/ CX)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
ms.openlocfilehash: 291766ade1397fee433198dce1a704949c8223c8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787512"
---
# <a name="override--ccli-and-ccx"></a>Przesłoń (C + +/ CLI i C + +/ CX)

**Zastąpienia** kontekstowe słowo kluczowe wskazuje, że składowej typu zastępuje klasy bazowej lub składowej interfejsu podstawowego.

## <a name="remarks"></a>Uwagi

**Zastąpienia** — słowo kluczowe jest prawidłowy, podczas kompilowania dla natywnych obiektów docelowych (opcja kompilatora domyślna), elementy docelowe środowisko uruchomieniowe Windows (`/ZW` — opcja kompilatora), lub obiektów docelowych środowiska uruchomieniowego języka wspólnego (`/clr` — opcja kompilatora).

Aby uzyskać więcej informacji na temat nadpisania specyfikatorów, zobacz [specyfikator override](../cpp/override-specifier.md) i [zastąpienie specyfikatorów i kompilacji macierzystych](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Aby uzyskać więcej informacji na temat kontekstowych słów kluczowych, zobacz [Context-Sensitive Keywords](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Przykłady

Poniższy przykład kodu pokazuje, że **zastąpienia** może również służyć w kompilacjach kodu natywnego.

```cpp
// override_keyword_1.cpp
// compile with: /c
struct I1 {
   virtual void f();
};

struct X : public I1 {
   virtual void f() override {}
};
```

### <a name="example"></a>Przykład

Poniższy przykład kodu pokazuje, że **zastąpienia** mogą być używane w kompilacjach środowiska wykonawczego Windows.

```cpp
// override_keyword_2.cpp
// compile with: /ZW /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Wymagania

— Opcja kompilatora: `/ZW`

### <a name="example"></a>Przykład

Poniższy przykład kodu pokazuje, że **zastąpienia** mogą być używane w typowych kompilacje środowiska uruchomieniowego języka.

```cpp
// override_keyword_3.cpp
// compile with: /clr /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Wymagania

— Opcja kompilatora: `/clr`

## <a name="see-also"></a>Zobacz też

[override, specyfikator](../cpp/override-specifier.md)<br/>
[Specyfikatory przesłonięć](override-specifiers-cpp-component-extensions.md)