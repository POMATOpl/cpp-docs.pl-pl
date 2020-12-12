---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK1312'
title: Błąd narzędzi konsolidatora LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: d861b6976f9b065e3a693e916164879a3311d3db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193633"
---
# <a name="linker-tools-error-lnk1312"></a>Błąd narzędzi konsolidatora LNK1312

nieprawidłowy lub uszkodzony plik: nie można zaimportować zestawu

Podczas kompilowania zestawu, plik inny niż moduł lub zestaw skompilowany z **/CLR** został przekazano do **/ASSEMBLYMODULE** opcji konsolidatora.  Jeśli przeszedł plik obiektu do **/ASSEMBLYMODULE**, wystarczy przekazać obiekt bezpośrednio do konsolidatora, a nie do **/ASSEMBLYMODULE**.

## <a name="examples"></a>Przykłady

Poniższy przykład utworzył plik. obj.

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

Poniższy przykład generuje LNK1312.

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
