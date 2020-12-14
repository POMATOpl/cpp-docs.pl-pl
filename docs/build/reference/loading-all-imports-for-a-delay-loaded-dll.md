---
description: 'Dowiedz się więcej na temat: ładowanie wszystkich importów dla Delay-Loaded DLL'
title: Importy Załaduj wszystko dla bibliotek DLL załadowanych z opóźnieniem
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: 0f1334f30568e4722bd97579145ddcae9851b901
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190926"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Importy Załaduj wszystko dla bibliotek DLL załadowanych z opóźnieniem

Funkcja **__HrLoadAllImportsForDll** , która jest zdefiniowana w Delayhlp. cpp, nakazuje konsolidatorowi załadowanie wszystkich importów z biblioteki DLL, która została określona za pomocą opcji konsolidatora [/DELAYLOAD](delayload-delay-load-import.md) .

Załadowanie wszystkich importów pozwala na umieszczenie obsługi błędów w jednym miejscu w kodzie i nie musi używać obsługi wyjątków wokół rzeczywistych wywołań importu. Pozwala również uniknąć sytuacji, w której aplikacja nie przestanie działać częściowo przez proces w wyniku kodu pomocnika, który nie może załadować importu.

Wywołanie **__HrLoadAllImportsForDll** nie zmienia zachowania punktów zaczepienia i obsługi błędów; Aby uzyskać więcej informacji, zobacz temat [Obsługa błędów i powiadomienia](error-handling-and-notification.md) .

Nazwa biblioteki DLL przeniesiona do **__HrLoadAllImportsForDll** jest porównywana z nazwą przechowywaną wewnątrz biblioteki DLL i jest uwzględniana wielkość liter.

Poniższy przykład pokazuje, jak wywołać **__HrLoadAllImportsForDll**:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>Zobacz też

[Obsługa konsolidatora dla Delay-Loaded bibliotek DLL](linker-support-for-delay-loaded-dlls.md)
