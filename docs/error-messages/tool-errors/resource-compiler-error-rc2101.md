---
description: 'Dowiedz się więcej na temat: błąd kompilatora zasobów zasobów RC2101'
title: Błąd kompilatora zasobów RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: bed2490f48f40c94724fa249f7722a290cf8d9b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164136"
---
# <a name="resource-compiler-error-rc2101"></a>Błąd kompilatora zasobów RC2101

Nieprawidłowa dyrektywa w wstępnie przetworzonym pliku RC

Plik kompilatora zasobów zawiera dyrektywę **#pragma** .

Użyj dyrektywy preprocesora **#ifndef** ze stałą RC_INVOKED, którą kompilator zasobów definiuje podczas przetwarzania pliku dołączanego. Umieść dyrektywę **#pragma** wewnątrz bloku kodu, który nie jest przetwarzany, gdy zostanie zdefiniowana stała RC_INVOKED. Kod w bloku jest przetwarzany tylko przez kompilator C/C++, a nie przez kompilator zasobów. Następujący przykładowy kod demonstruje tę technikę:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

Dyrektywa preprocesora **#pragma** nie ma znaczenia w. Plik RC. Dyrektywa preprocesora **#include** jest często używana w. Plik RC obejmujący plik nagłówka (plik niestandardowego nagłówka bazujący na projekcie lub standardowy plik nagłówkowy dostarczany przez firmę Microsoft z jednym z jego produktów). Niektóre z tych plików dołączanych zawierają dyrektywę **#pragma** . Ponieważ plik nagłówkowy może zawierać jeden lub więcej innych plików nagłówkowych, plik zawierający **nie#pragmaą** dyrektywę może nie być natychmiast oczywisty.

Technikę RC_INVOKED **#ifndef** może kontrolować, w tym pliki nagłówkowe w plikach nagłówkowych opartych na projekcie.
