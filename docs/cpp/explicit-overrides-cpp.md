---
title: Jawne przesłonięcia (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- virtual functions [C++], explicit overrides
- overriding, functions
- derived classes [C++], virtual functions
- explicit virtual function overrides
- explicit override of virtual function
ms.assetid: ee583234-5cda-4e90-b55e-3f9fbf079ced
ms.openlocfilehash: dbaf8b0d78093df522cfbc63bf20dd0acb6c477c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184257"
---
# <a name="explicit-overrides-c"></a>Jawne przesłonięcia (C++)

**Microsoft Specific**

Jeśli ten sam funkcji wirtualna jest zadeklarowana w co najmniej dwóch [interfejsów](../cpp/interface.md) i jeśli klasa jest pochodną tych interfejsów, można wyraźnie przezwyciężyć każdej funkcji wirtualnej.

Instrukcje dotyczące jawne przesłonięcia przy użyciu kodu zarządzanego C++sposób niezamierzony, zobacz [jawne zastępowanie](../extensions/explicit-overrides-cpp-component-extensions.md).

**END specyficzny dla Microsoft**

## <a name="example"></a>Przykład

Poniższy przykład kodu ilustruje sposób użycia jawne przesłonięcia:

```cpp
// deriv_ExplicitOverrides.cpp
// compile with: /GR
extern "C" int printf_s(const char *, ...);

__interface IMyInt1 {
   void mf1();
   void mf1(int);
   void mf2();
   void mf2(int);
};

__interface IMyInt2 {
   void mf1();
   void mf1(int);
   void mf2();
   void mf2(int);
};

class CMyClass : public IMyInt1, public IMyInt2 {
public:
   void IMyInt1::mf1() {
      printf_s("In CMyClass::IMyInt1::mf1()\n");
   }

   void IMyInt1::mf1(int) {
      printf_s("In CMyClass::IMyInt1::mf1(int)\n");
   }

   void IMyInt1::mf2();
   void IMyInt1::mf2(int);

   void IMyInt2::mf1() {
      printf_s("In CMyClass::IMyInt2::mf1()\n");
   }

   void IMyInt2::mf1(int) {
         printf_s("In CMyClass::IMyInt2::mf1(int)\n");
   }

   void IMyInt2::mf2();
   void IMyInt2::mf2(int);
};

void CMyClass::IMyInt1::mf2() {
   printf_s("In CMyClass::IMyInt1::mf2()\n");
}

void CMyClass::IMyInt1::mf2(int) {
   printf_s("In CMyClass::IMyInt1::mf2(int)\n");
}

void CMyClass::IMyInt2::mf2() {
   printf_s("In CMyClass::IMyInt2::mf2()\n");
}

void CMyClass::IMyInt2::mf2(int) {
   printf_s("In CMyClass::IMyInt2::mf2(int)\n");
}

int main() {
   IMyInt1 *pIMyInt1 = new CMyClass();
   IMyInt2 *pIMyInt2 = dynamic_cast<IMyInt2 *>(pIMyInt1);

   pIMyInt1->mf1();
   pIMyInt1->mf1(1);
   pIMyInt1->mf2();
   pIMyInt1->mf2(2);
   pIMyInt2->mf1();
   pIMyInt2->mf1(3);
   pIMyInt2->mf2();
   pIMyInt2->mf2(4);

   // Cast to a CMyClass pointer so that the destructor gets called
      CMyClass *p = dynamic_cast<CMyClass *>(pIMyInt1);
      delete p;
}
```

```Output
In CMyClass::IMyInt1::mf1()
In CMyClass::IMyInt1::mf1(int)
In CMyClass::IMyInt1::mf2()
In CMyClass::IMyInt1::mf2(int)
In CMyClass::IMyInt2::mf1()
In CMyClass::IMyInt2::mf1(int)
In CMyClass::IMyInt2::mf2()
In CMyClass::IMyInt2::mf2(int)
```

## <a name="see-also"></a>Zobacz także

[Dziedziczenie](../cpp/inheritance-cpp.md)