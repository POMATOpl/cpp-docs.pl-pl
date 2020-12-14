---
description: 'Dowiedz się więcej na temat: Błąd narzędzi konsolidatora LNK2033'
title: Błąd narzędzi konsolidatora LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 46ee94e0aff4379a6d28a508ed1394e90ef9a96d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275649"
---
# <a name="linker-tools-error-lnk2033"></a>Błąd narzędzi konsolidatora LNK2033

nierozpoznany token TypeRef (token) dla elementu "Type"

Typ nie ma definicji w metadanych MSIL.

LNK2033 może wystąpić podczas kompilowania z **/CLR: Safe** i w przypadku, gdy istnieje tylko Deklaracja do przodu dla typu w module MSIL, gdzie do tego typu odwołuje się moduł MSIL.

Typ musi być zdefiniowany w opcji **/CLR: Safe**.

Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje LNK2033.

```cpp
// LNK2033.cpp
// compile with: /clr:safe
// LNK2033 expected
ref class A;
ref class B {};

int main() {
   A ^ aa = nullptr;
   B ^ bb = nullptr;   // OK
};
```
