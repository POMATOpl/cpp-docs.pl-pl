---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4635'
title: Ostrzeżenie kompilatora (poziom 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: e885c501e4f10719618bb552c153dc13a481332d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168335"
---
# <a name="compiler-warning-level-3-c4635"></a>Ostrzeżenie kompilatora (poziom 3) C4635

Obiekt docelowy komentarza dokumentu XML: nieprawidłowo sformułowany kod XML: Przyczyna

Kompilator wykrył jakiś problem z tagami XML.  Usuń problem i ponownie skompiluj

Poniższy przykład generuje C4635:

```cpp
// C4635.cpp
// compile with: /doc /clr /W3 /c
/// <summary>
/// The contents of the folder have changed.
/// <summary/>   // C4635

// try the following line instead
// /// </summary>
public ref class Test {};
```

Zwróć uwagę, że dane wyjściowe dla tego przykładu brzmią: **tag końcowy "member" jest niezgodny z tagiem początkowym "Summary".**

Problem z tym przykładem polega na tym, że tag końcowy \<summary> jest źle sformułowany, a kompilator nie rozpoznaje go jako \<summary> tag końcowy.  \<member>Tag jest osadzony w pliku. xdc przez kompilator w każdej kompilacji/doc.  Dlatego problem polega na tym, że tag końcowy \</member> nie jest zgodny z poprzednim tagiem początkowym przetworzonym przez kompilator ( \<summary> .
