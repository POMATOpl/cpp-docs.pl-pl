---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1107'
title: Błąd narzędzi konsolidatora LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: 2a5ed9ba0bc4789a324d143b6287a08712299cdd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281395"
---
# <a name="linker-tools-error-lnk1107"></a>Błąd narzędzi konsolidatora LNK1107

nieprawidłowy lub uszkodzony plik: nie można odczytać w lokalizacji

Narzędzie nie może odczytać pliku. Utwórz ponownie plik.

LNK1107 może również wystąpić, jeśli spróbujesz przekazać moduł (. dll lub rozszerzenie modułu utworzonego za pomocą [/CLR: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) lub  [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)) do konsolidatora; Zamiast tego Przekaż plik. obj.

Jeśli kompilujesz następujący przykład:

```cpp
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

a następnie określ **LNK1107.dllłącza** w wierszu polecenia, uzyskasz LNK1107.  Aby rozwiązać ten problem, należy zamiast tego określić **link LNK1107. obj** .
