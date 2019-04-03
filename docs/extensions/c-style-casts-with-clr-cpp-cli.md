---
title: Stylu C rzutuje z / clr (C + +/ CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
ms.openlocfilehash: 31dc0db16e960e640c08249e78e710950778a927
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787527"
---
# <a name="c-style-casts-with-clr-ccli"></a>Rzutowania w stylu C i kompilator /clr (C++/CLI)

Poniższy temat dotyczy tylko środowiska uruchomieniowego języka wspólnego.

W przypadku użycia z typami CLR, kompilator próbuje zamapować C rzutowania w stylu do jednego z rzutowania wymienione poniżej pod warunkiem w następującej kolejności:

1. const_cast

2. safe_cast

3. safe_cast, a także operator const_cast

4. static_cast

5. static_cast plus const_cast

Jeśli żaden z rzutowania wymienionych powyżej nie jest prawidłowy i typ wyrażenia i typ docelowy są typami odwołań CLR, rzutowania w stylu C jest mapowany na sprawdzanie czasu wykonywania (castclass instrukcji MSIL). W przeciwnym razie rzutowania w stylu C jest uznawane za nieprawidłowe i kompilator generuje błąd.

## <a name="remarks"></a>Uwagi

Rzutowania w stylu języka C nie jest zalecane. Podczas kompilowania za pomocą [/CLR (kompilacja języka wspólnego środowiska uruchomieniowego)](../build/reference/clr-common-language-runtime-compilation.md), użyj [safe_cast](safe-cast-cpp-component-extensions.md).

Poniższy przykład pokazuje C rzutowania w stylu mapowana na **const_cast**.

```cpp
// cstyle_casts_1.cpp
// compile with: /clr
using namespace System;

ref struct R {};
int main() {
   const R^ constrefR = gcnew R();
   R^ nonconstR = (R^)(constrefR);
}
```

Poniższy przykład pokazuje C rzutowania w stylu mapowana na **safe_cast**.

```cpp
// cstyle_casts_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Object ^ o = "hello";
   String ^ s = (String^)o;
}
```

Poniższy przykład pokazuje C rzutowania w stylu mapowana na **safe_cast** oraz **const_cast**.

```cpp
// cstyle_casts_3.cpp
// compile with: /clr
using namespace System;

ref struct R {};
ref struct R2 : public R {};

int main() {
   const R^ constR2 = gcnew R2();
   try {
   R2^ b2DR = (R2^)(constR2);
   }
   catch(InvalidCastException^ e) {
      System::Console::WriteLine("Invalid Exception");
   }
}
```

Poniższy przykład pokazuje C rzutowania w stylu mapowana na **static_cast**.

```cpp
// cstyle_casts_4.cpp
// compile with: /clr
using namespace System;

struct N1 {};
struct N2 {
   operator N1() {
      return N1();
   }
};

int main() {
   N2 n2;
   N1 n1 ;
   n1 = (N1)n2;
}
```

Poniższy przykład pokazuje C rzutowania w stylu mapowana na **static_cast** oraz **const_cast**.

```cpp
// cstyle_casts_5.cpp
// compile with: /clr
using namespace System;
struct N1 {};

struct N2 {
   operator const N1*() {
      static const N1 n1;
      return &n1;
   }
};

int main() {
   N2 n2;
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast
}
```

Poniższy przykład pokazuje C rzutowania w stylu mapowana na sprawdzanie w czasie wykonania.

```cpp
// cstyle_casts_6.cpp
// compile with: /clr
using namespace System;

ref class R1 {};
ref class R2 {};

int main() {
   R1^ r  = gcnew R1();
   try {
      R2^ rr = ( R2^)(r);
   }
   catch(System::InvalidCastException^ e) {
      Console::WriteLine("Caught expected exception");
   }
}
```

Poniższy przykład pokazuje nieprawidłowy C rzutowania w stylu, co powoduje, że kompilator na błąd.

```cpp
// cstyle_casts_7.cpp
// compile with: /clr
using namespace System;
int main() {
   String^s = S"hello";
   int i = (int)s;   // C2440
}
```

## <a name="requirements"></a>Wymagania

— Opcja kompilatora: `/clr`

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platformy .NET i platformy uniwersalnej systemu Windows](component-extensions-for-runtime-platforms.md)