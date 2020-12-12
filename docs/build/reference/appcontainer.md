---
description: Dowiedz się więcej na temat:/APPCONTAINER
title: /APPCONTAINER
ms.date: 11/04/2016
f1_keywords:
- /APPCONTAINER
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
ms.openlocfilehash: f9ea7ff8cac45e45626f15745f77d2230afc1d4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187172"
---
# <a name="appcontainer"></a>/APPCONTAINER

Oznacza plik wykonywalny, który musi być uruchamiany w kontenerze aplikacji — na przykład Microsoft Store lub uniwersalnej aplikacji systemu Windows.

```

/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Uwagi

Plik wykonywalny z zestawem opcji **/APPCONTAINER** można uruchomić tylko w kontenerze aplikacji, który jest środowiskiem izolacji procesu wprowadzonym w systemie Windows 8. Dla Microsoft Store i uniwersalnych aplikacji systemu Windows należy ustawić tę opcję.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)<br/>
[Co to jest aplikacja uniwersalna systemu Windows?](/windows/uwp/get-started/universal-application-platform-guide)
