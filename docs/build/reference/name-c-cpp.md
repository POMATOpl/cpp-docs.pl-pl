---
description: 'Dowiedz się więcej na temat: Nazwa (C/C++)'
title: NAZWA (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: 7444aa20539b47b1f04d17a266a0b65a552af3f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137777"
---
# <a name="name-cc"></a>NAZWA (C/C++)

Określa nazwę głównego pliku wyjściowego.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Uwagi

Odpowiednikiem metody określania nazwy pliku wyjściowego jest z opcją konsolidatora [/out](out-output-file-name.md) , a odpowiednikiem sposobu ustawiania adresu podstawowego jest [/Base](base-base-address.md) opcji konsolidatora. Jeśli oba są określone,/OUT zastępuje **nazwę**.

W przypadku kompilowania biblioteki DLL nazwa będzie miała wpływ tylko na nazwę biblioteki DLL.

## <a name="see-also"></a>Zobacz też

[Reguły dla instrukcji Module-Definition](rules-for-module-definition-statements.md)
