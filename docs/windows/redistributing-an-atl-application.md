---
description: 'Dowiedz się więcej o programie: Redystrybuowanie aplikacji ATL'
title: Ponowna dystrybucja aplikacji ATL
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
ms.openlocfilehash: 58021416eb7f258e1d436ff099ebf9c647dfc0bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179957"
---
# <a name="redistributing-an-atl-application"></a>Ponowna dystrybucja aplikacji ATL

Począwszy od programu Visual Studio 2012, Active Template Library (ATL) jest biblioteką tylko do nagłówka. Projekty ATL nie mają opcji dynamicznego łączenia z ATL. Biblioteka ATL redystrybucyjna nie jest wymagana.

W przypadku ponownej dystrybucji aplikacji wykonywalnej ATL należy zarejestrować plik exe (i wszystkie kontrolki wewnątrz niego), wydając następujące polecenie:

```
filename /regserver
```

gdzie `filename` jest nazwą pliku wykonywalnego.

W programie Visual Studio 2010 Projekt ATL można skompilować dla konfiguracji MinDependency lub MinSize. Konfiguracja MinDependency jest pobierana podczas ustawiania **użycia właściwości ATL** do **statycznego łącza do ATL** na stronie właściwości **Ogólne** i ustawiania właściwości **Biblioteka środowiska uruchomieniowego** na **wiele wątków (/MT)** na stronie właściwości **generowania kodu** (folder C/C++).

Konfiguracja MinSize jest pobierana, gdy ustawiasz użycie właściwości **ATL** na **dynamiczny link do ATL** na stronie właściwości **Ogólne** lub ustaw właściwość **Biblioteka środowiska uruchomieniowego** na **wielowątkową bibliotekę DLL (/MD)** na stronie właściwości **generowania kodu** (folder C/C++).

MinSize sprawia, że plik wyjściowy jest możliwie mały, ale wymaga ATL100.dll i Msvcr100.dll (w przypadku wybrania opcji **/MD)** na komputerze docelowym. ATL100.dll powinna być zarejestrowana na komputerze docelowym, aby upewnić się, że wszystkie funkcje ATL są obecne. ATL100.dll zawiera operacje eksportowania ANSI i Unicode.

Jeśli tworzysz projekt szablonów ATL lub OLE DB dla elementu docelowego MinDependency, nie musisz instalować ani rejestrować ATL100.dll na komputerze docelowym, ale może zostać wyświetlony większy obraz programu.

W przypadku ponownej dystrybucji aplikacji wykonywalnej ATL należy zarejestrować plik exe (i wszystkie kontrolki wewnątrz niego), wydając następujące polecenie:

```
filename /regserver
```

gdzie `filename` jest nazwą pliku wykonywalnego.

## <a name="see-also"></a>Zobacz też

[Ponowne dystrybuowanie plików programu Visual C++](redistributing-visual-cpp-files.md)
