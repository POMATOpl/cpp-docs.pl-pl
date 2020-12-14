---
description: 'Dowiedz się więcej o: LNK4247 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4247 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: 88cd04e345b798b6927c3a5297380f1eeb3c5f5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241186"
---
# <a name="linker-tools-warning-lnk4247"></a>Ostrzeżenie LNK4247 narzędzi konsolidatora

punkt wejścia "decorated_function_name" ma już atrybut wątku; Zignorowano element "Attribute"

Punkt wejścia określony za pomocą elementu [/entry (symbol punktu wejścia)](../../build/reference/entry-entry-point-symbol.md)ma atrybut Threading, ale określono również [/CLRTHREADATTRIBUTE (ustaw atrybut wątku CLR)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) z innym modelem wątkowości.

Konsolidator zignorował wartość określoną za pomocą/CLRTHREADATTRIBUTE.

Aby usunąć to ostrzeżenie:

- Usuń/CLRTHREADATTRIBUTE z kompilacji.

- Usuń atrybut z pliku kodu źródłowego.

- Usuń atrybut ze źródła i/CLRTHREADATTRIBUTE z kompilacji i Zaakceptuj domyślny model wątkowości CLR.

- Zmień wartość przekazaną do/CLRTHREADATTRIBUTE, tak aby była ona zgodna z atrybutem w źródle.

- Zmień atrybut w elemencie source, tak aby zgadzał się z wartością przekazaną do/CLRTHREADATTRIBUTE.

Poniższy przykład generuje LNK4247 narzędzi KONSOLIDATORA

```cpp
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```
