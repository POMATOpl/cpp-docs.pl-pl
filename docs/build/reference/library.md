---
description: 'Dowiedz się więcej o bibliotece: Biblioteka'
title: BIBLIOTEKA
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: 3d8c63f323568949cf2fb30935d2557755346422
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199535"
---
# <a name="library"></a>BIBLIOTEKA

Informuje LINK, aby utworzyć bibliotekę DLL. W tym samym czasie, LINK tworzy bibliotekę importu, chyba że plik EXP jest używany w kompilacji.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Uwagi

Argument *biblioteki* określa nazwę biblioteki DLL. Można również użyć opcji konsolidatora [/out](out-output-file-name.md) , aby określić nazwę WYJŚCIOWĄ biblioteki DLL.

Argument BASE =*Address* ustawia adres podstawowy, którego system operacyjny używa do ZAŁADOWANIA biblioteki DLL. Ten argument zastępuje domyślną lokalizację DLL 0x10000000. Zobacz opis opcji [/Base](base-base-address.md) , aby uzyskać szczegółowe informacje na temat adresów podstawowych.

Pamiętaj, aby użyć opcji konsolidatora [/dll](dll-build-a-dll.md) podczas KOMPILOWANIA biblioteki DLL.

## <a name="see-also"></a>Zobacz też

[Reguły dla instrukcji Module-Definition](rules-for-module-definition-statements.md)
