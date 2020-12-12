---
description: 'Dowiedz się więcej o: #error dyrektywie (C/C++)'
title: '#error, dyrektywa (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: fd6503de9590893ee0ec53cbbfa59429a0cfdcfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261154"
---
# <a name="error-directive-cc"></a>#error — dyrektywa (C/C++)

Dyrektywa **#error** emituje określony przez użytkownika komunikat o błędzie w czasie kompilacji, a następnie kończy kompilację.

## <a name="syntax"></a>Składnia

> token **#error** *— ciąg*

## <a name="remarks"></a>Uwagi

Komunikat o błędzie, który jest emitowany przez tę dyrektywę, zawiera parametr *token-String* . Parametr *tokenu-String* nie podlega rozszerzeniu makra. Ta dyrektywa jest najbardziej przydatna podczas przetwarzania wstępnego, w celu powiadomienia dewelopera niespójności programu lub naruszenia ograniczenia. Poniższy przykład ilustruje przetwarzanie błędów podczas przetwarzania wstępnego:

```cpp
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>Zobacz też

[Dyrektywy preprocesora](../preprocessor/preprocessor-directives.md)
