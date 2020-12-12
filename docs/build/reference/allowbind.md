---
description: Dowiedz się więcej na temat:/ALLOWBIND
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 54f3056240537d765a9212e774a9a313ded49dab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179606"
---
# <a name="allowbind"></a>/ALLOWBIND

Określa, czy można powiązać bibliotekę DLL.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Uwagi

Opcja **/ALLOWBIND** ustawia bit w nagłówku dll, który wskazuje na Bind.exe, że można powiązać obraz. Powiązanie może umożliwić szybsze ładowanie obrazu, gdy moduł ładujący nie musi zmienić bazy i wykonać naprawy adresu dla każdej biblioteki DLL, do której się odwołuje. Nie ma potrzeby powiązania DLL, jeśli został on podpisany cyfrowo — powiązanie unieważnia sygnaturę. Powiązanie nie ma wpływu, jeśli jest włączone generowanie losowe układu przestrzeni adresowej (ASLR) dla obrazu za pomocą **/DYNAMICBASE** w wersjach systemu Windows, które obsługują ASLR.

Użyj **/ALLOWBIND: nie** , aby zapobiec powiązaniu Bind.exe z biblioteką DLL.

Aby uzyskać więcej informacji, zobacz [/ALLOWBIND](allowbind-prevent-dll-binding.md) — opcja konsolidatora.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)
