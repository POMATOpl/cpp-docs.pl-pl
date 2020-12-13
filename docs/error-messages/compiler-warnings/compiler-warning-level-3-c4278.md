---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4278'
title: Ostrzeżenie kompilatora (poziom 3) C4278
ms.date: 08/27/2018
f1_keywords:
- C4278
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
ms.openlocfilehash: f7a53b54422e28f94096b91502651cb9355a244e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344149"
---
# <a name="compiler-warning-level-3-c4278"></a>Ostrzeżenie kompilatora (poziom 3) C4278

> "*Identyfikator*": identyfikator w bibliotece typów "*TLB*" jest już makrem; Użyj kwalifikatora "Rename"

W przypadku korzystania z [#import](../../preprocessor/hash-import-directive-cpp.md)identyfikator w importowanym elemencie TypeLib próbuje zadeklarować *Identyfikator* identyfikatora. Jednak ten symbol jest już prawidłowy.

Użyj atrybutu `#import` **zmiany nazwy** , aby przypisać alias do symbolu w bibliotece typów.
