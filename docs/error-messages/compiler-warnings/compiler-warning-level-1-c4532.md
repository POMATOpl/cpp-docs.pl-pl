---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4532'
title: Ostrzeżenie kompilatora (poziom 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: 9468ca1242397289c832fec28d71cf245c6c8a5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294811"
---
# <a name="compiler-warning-level-1-c4532"></a>Ostrzeżenie kompilatora (poziom 1) C4532

"Kontynuuj": Wyskocz z __finally bloku/finally ma niezdefiniowane zachowanie podczas obsługi zakończenia

Kompilator napotkał jedno z następujących słów kluczowych:

- [utrzymać](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

powodowanie przejścia z [__finally](../../cpp/try-finally-statement.md) lub [finally](../../dotnet/finally.md) bloku podczas nietypowego zakończenia.

Jeśli wystąpi wyjątek, a podczas gdy stos jest usuwany podczas wykonywania programów obsługi zakończenia ( **`__finally`** lub bloków finally), a kod przechodzi z **`__finally`** bloku przed **`__finally`** zakończeniem bloku, zachowanie jest niezdefiniowane. Formant nie może powrócić do kodu odwinięcia, więc wyjątek może nie być obsługiwany prawidłowo.

Jeśli musisz wyskoczyć z **`__finally`** bloku, najpierw sprawdź, czy nie określono nietypowego zakończenia.

Poniższy przykład generuje C4532; po prostu Dodaj komentarz do instrukcji skoku, aby rozwiązać ostrzeżenia.

```cpp
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```
