---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4191'
title: Ostrzeżenie kompilatora (poziom 3) C4191
ms.date: 11/04/2016
f1_keywords:
- C4191
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
ms.openlocfilehash: 0a34147a8cdba7e21af706711e5aa433939188ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344240"
---
# <a name="compiler-warning-level-3-c4191"></a>Ostrzeżenie kompilatora (poziom 3) C4191

"operator/Operation": niebezpieczna konwersja z typu wyrażenia na typ "Required"

Kilka operacji obejmujących wskaźniki funkcji są uważane za niebezpieczne:

- Typy funkcji z różnymi konwencjami wywoływania.

- Typy funkcji z różnymi konwencjami powrotu.

- Argumenty lub typy zwracane z różnymi rozmiarami, kategoriami typów lub klasyfikacjami.

- Różne długości list argumentów (włączone **`__cdecl`** , tylko na rzutach z dłuższej listy do krótszej listy, nawet jeśli krótszy jest VarArgs).

- Wskaźnik do danych (innych niż **`void`** <strong>\*</strong> ) aliasowany względem wskaźnika do działania.

- Wszelkie inne różnice typu, które mogą spowodować błąd lub ostrzeżenie na **`reinterpret_cast`** .

Wywołanie tej funkcji za pomocą wskaźnika wynikowego może spowodować awarię programu.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4191:

```cpp
// C4191.cpp
// compile with: /W3 /clr
#pragma warning(default: 4191)

void __clrcall f1() { }
void __cdecl   f2() { }

typedef void (__clrcall * fnptr1)();
typedef void (__cdecl   * fnptr2)();

int main() {
   fnptr1 fp1 = static_cast<fnptr1>(&f1);
   fnptr2 fp2 = (fnptr2) &f2;

   fnptr1 fp3 = (fnptr1) &f2;   // C4191
   fnptr2 fp4 = (fnptr2) &f1;   // C4191
};
```
