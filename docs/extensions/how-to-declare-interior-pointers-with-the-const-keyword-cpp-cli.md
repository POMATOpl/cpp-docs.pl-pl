---
title: 'Instrukcje: Deklarowanie wewnętrznych wskaźników za pomocą słowa kluczowego const (C + +/ CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, interior
ms.assetid: 64e08b0e-9396-4046-ab51-8f6588f32330
ms.openlocfilehash: 22e190edb1f3e7a971a650c6db9af0e57d1034a5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787551"
---
# <a name="how-to-declare-interior-pointers-with-the-const-keyword-ccli"></a>Instrukcje: Deklarowanie wewnętrznych wskaźników za pomocą słowa kluczowego const (C + +/ CLI)

Poniższy przykład pokazuje sposób użycia **const** w deklaracji wskaźnika wewnętrznego.

> [!IMPORTANT]
> Tej funkcji języka jest obsługiwana przez `/clr` — opcja kompilatora, ale nie za `/ZW` — opcja kompilatora.

## <a name="example"></a>Przykład

```cpp
// interior_ptr_const.cpp
// compile with: /clr
using namespace System;
value struct V {
   int i;
};

ref struct G {
   V v;
   String ^ msg;
};

interior_ptr<int> f( interior_ptr<V> pv ) {
   return &(pv->i);
}

int main() {
   int n = -1;
   int o = -1;
   interior_ptr<int> pn1 = &n;
   *pn1 = 50;

   V v;
   v.i = 101;
   V * npV = &v;   // ok: &v yields a pointer to the native heap

   interior_ptr<int> pn2 = &n;
   interior_ptr<V> pV = &(v);
   pn2 = f(pV);
   *pn2 = 50;

   G ^pG = gcnew G;
   pV = &(pG->v);   // ok: pV is an interior pointer

   interior_ptr<int const> pn3 = &n;
   // *pn3 = 5;   error because pn3 cannot be dereferenced and changed
   pn3 = &o;   // OK, can change the memory location

   interior_ptr<int> const pn4 = &n;
   *pn4 = 5;   // OK because you can dereference and change pn4
   // pn4 = &o;   error cannot change the memory location

   const interior_ptr<const int> pn5 = &n;
   // *pn5 = 5;   error cannot dereference and change pn5
   // pn5 = &o;   error cannot change the memory location

   const G ^ h_G = gcnew G;   // object is const, cannot modify any members of h_G or call any non-const methods
   // h_G->msg = "test";   error h_G is const
   interior_ptr<String^ const> int_ptr_G = &(h_G->msg);

   G ^ const h_G2 = gcnew G;   // interior pointers to this obejct cannot be dereferenced and changed
   h_G2->msg = "test";
   interior_ptr<String^ const> int_ptr_G2 = &(h_G->msg);
};
```

## <a name="see-also"></a>Zobacz też

[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)