---
description: 'Dowiedz się więcej na temat: wymagania dotyczące kompilacji wspólnych kontrolek systemu Windows'
title: Wymagania dotyczące kompilacji dla formantów standardowych systemu Windows
ms.date: 08/19/2019
helpviewer_keywords:
- Common Controls (MFC), build requirements
- Common Controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: 4d11b4da2fb1ff616ab077390c2d603e76382313
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339803"
---
# <a name="build-requirements-for-windows-common-controls"></a>Wymagania dotyczące kompilacji dla formantów standardowych systemu Windows

Biblioteka Microsoft Foundation Class (MFC) obsługuje [Formanty standardowe systemu Windows](/windows/win32/controls/common-controls-intro). Formanty standardowe są zawarte w systemie Windows, a biblioteka jest uwzględniona w programie Visual Studio. Biblioteka MFC zawiera nowe metody, które rozszerzają istniejące klasy, oraz dodatkowe klasy i metody obsługujące typowe formanty systemu Windows. Podczas kompilowania aplikacji należy postępować zgodnie z wymaganiami dotyczącymi kompilacji i migracji, które zostały opisane w poniższych sekcjach.

## <a name="compilation-requirements"></a>Wymagania dotyczące kompilacji

### <a name="supported-versions"></a>Obsługiwane wersje

MFC obsługuje wszystkie wersje wspólnych kontrolek. Aby uzyskać informacje o wersjach typowych kontrolek systemu Windows, zobacz [popularne wersje kontroli](/windows/win32/controls/common-control-versions).

### <a name="supported-character-sets"></a>Obsługiwane zestawy znaków

Formanty wspólne systemu Windows obsługują tylko zestaw znaków Unicode, a nie zestaw znaków ANSI. W przypadku kompilowania aplikacji w wierszu polecenia Użyj obu następujących opcji kompilatora Definiuj (/D), aby określić Unicode jako podstawowy zestaw znaków:

```
/D_UNICODE /DUNICODE
```

W przypadku kompilowania aplikacji w zintegrowanym środowisku programistycznym (IDE) programu Visual Studio określ opcję **zestaw znaków Unicode** właściwości **zestaw znaków** w węźle **Ogólne** właściwości projektu.

## <a name="migration-requirements"></a>Wymagania dotyczące migracji

Jeśli używasz środowiska IDE programu Visual Studio do utworzenia nowej aplikacji MFC, która używa formantów wspólnych systemu Windows, IDE automatycznie deklaruje odpowiedni manifest. Jednak w przypadku migrowania istniejącej aplikacji MFC z programu Visual Studio 2005 lub starszej, a użytkownik chce używać tych standardowych formantów, IDE nie dostarcza automatycznie informacji manifestu w celu uaktualnienia aplikacji. Zamiast tego należy ręcznie wstawić następujący kod źródłowy do prekompilowanego pliku nagłówkowego:

```
#ifdef UNICODE
#if defined _M_IX86
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_IA64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_X64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#else
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")
#endif
#endif
```

## <a name="see-also"></a>Zobacz też

[Ogólne tematy dotyczące MFC](general-mfc-topics.md)<br/>
[Wykres hierarchii](hierarchy-chart.md)<br/>
[Przestarzałe interfejsy API ANSI](deprecated-ansi-apis.md)
