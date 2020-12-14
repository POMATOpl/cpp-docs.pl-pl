---
description: 'Dowiedz się więcej o: podstawienie makra'
title: Podstawianie makr
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 5e1531afb210b4671632bca2540bfc7562653139
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199184"
---
# <a name="macro-substitution"></a>Podstawianie makr

Gdy *Macroname* jest wywoływana, każde wystąpienie *ciąg1* w jego ciągu definicji jest zastępowane przez *ciąg2*.

## <a name="syntax"></a>Składnia

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Uwagi

Podstawianie makr uwzględnia wielkość liter i jest literałem; *ciąg1* i *ciąg2* nie mogą wywoływać makr. Podstawienie nie modyfikuje oryginalnej definicji. Można zastąpić tekst we wstępnie zdefiniowanym makrze z wyjątkiem [$$@](filename-macros.md) .

Spacje lub karty nie poprzedzają dwukropka; dowolny po dwukropek jest interpretowany jako literał. Jeśli *ciąg2* ma wartość null, wszystkie wystąpienia elementu *ciąg1* są usuwane z ciągu definicji makra.

## <a name="see-also"></a>Zobacz też

[Korzystanie z makra NMAKE](using-an-nmake-macro.md)
