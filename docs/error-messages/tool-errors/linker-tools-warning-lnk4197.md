---
description: 'Dowiedz się więcej o: LNK4197 narzędzi KONSOLIDATORA ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4197 narzędzi konsolidatora
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: a2054caf5e60cc7333c0da70c6027966536e8406
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294356"
---
# <a name="linker-tools-warning-lnk4197"></a>Ostrzeżenie LNK4197 narzędzi konsolidatora

> Eksport "*exportname*" określono wiele razy; Używanie pierwszej specyfikacji

Eksport jest określony na wiele różnych sposobów. Konsolidator używa pierwszej specyfikacji i ignoruje resztę.

W przypadku ponownego kompilowania biblioteki wykonawczej C można zignorować ten komunikat.

Jeśli eksport zostanie określony dokładnie tak samo jak wiele razy, konsolidator nie wystawia ostrzeżenia.

Na przykład następująca zawartość pliku. def spowoduje wystąpienie tego ostrzeżenia:

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Ten sam Eksport jest określony w wierszu polecenia (za pomocą eksportu:) i w pliku. def.

2. Ten sam Eksport jest wymieniony dwukrotnie w pliku. def z innymi atrybutami.
