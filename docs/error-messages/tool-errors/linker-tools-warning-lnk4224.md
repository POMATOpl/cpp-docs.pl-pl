---
description: 'Dowiedz się więcej o: LNK4224 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4224 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: 35cae5c46b91493a40d4d52650f781010f6d6379
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327906"
---
# <a name="linker-tools-warning-lnk4224"></a>Ostrzeżenie LNK4224 narzędzi konsolidatora

> *opcja* nie jest już obsługiwana; Ignoruj

## <a name="remarks"></a>Uwagi

Określono nieprawidłową, przestarzałą opcję konsolidatora i została zignorowana.

Na przykład LNK4224 narzędzi KONSOLIDATORA może wystąpić, jeśli dyrektywa/Comment pojawia się w. obj. Dyrektywa/Comment zostałaby dodana za pomocą [komentarza (C/C++)](../../preprocessor/comment-c-cpp.md) pragma przy użyciu przestarzałej opcji exestr. Użyj polecenia DUMPBIN [/All](../../build/reference/all.md) , aby wyświetlić dyrektywy konsolidatora w pliku. obj.

Jeśli to możliwe, zmodyfikuj Źródło dla. obj i Usuń pragmę. Jeśli zignorujesz to ostrzeżenie, istnieje możliwość, że plik wykonywalny skompilowany za pomocą **/CLR: Pure** nie będzie działać zgodnie z oczekiwaniami. **/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

## <a name="example"></a>Przykład

Poniższy przykład generuje LNK4224 narzędzi KONSOLIDATORA.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```
