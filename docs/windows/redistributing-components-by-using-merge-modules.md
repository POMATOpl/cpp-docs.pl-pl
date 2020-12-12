---
description: 'Dowiedz się więcej o programie: redystrybuuj składniki za pomocą modułów scalania'
title: Redystrybucja składników za pomocą modułów scalania
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: ecfc2904be7451c96226e91ed8e7f98d565d35ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179905"
---
# <a name="redistributing-components-by-using-merge-modules"></a>Redystrybucja składników za pomocą modułów scalania

Program Visual Studio zawiera [moduły scalania](/windows/win32/Msi/about-merge-modules) dla każdego składnika Visual C++, który jest licencjonowany do dystrybucji przy użyciu aplikacji. Gdy moduł scalania jest wkompilowany w plik instalacyjny Instalatora Windows, umożliwia on wdrażanie określonych bibliotek DLL na komputerach, które mają określoną platformę. W pliku konfiguracji należy określić, że moduły scalania stanowią wymagania wstępne dotyczące aplikacji. Po zainstalowaniu programu Visual Studio moduły scalania są instalowane w \Program Files\Common Files\Merge modules \\ . (Można redystrybuować tylko niedebugowane wersje bibliotek DLL Visual C++). Aby uzyskać więcej informacji i link do listy modułów scalania, które są licencjonowane do redystrybucji, zobacz [Redystrybuowanie plików Visual C++](redistributing-visual-cpp-files.md).

Za pomocą modułów scalania można włączyć instalację bibliotek DLL Visual C++ redystrybucyjnych w folderze%SYSTEMROOT%\system32\. (W programie Visual Studio jest stosowana ta technika). Jednak instalacja w tym folderze zakończy się niepowodzeniem, chyba że użytkownik instalujący prawa administratora.

Nie zalecamy korzystania z modułów scalania z wyjątkiem przypadków, kiedy nie musisz świadczyć serwisu aplikacji i nie zależy ona od więcej niż jednej wersji biblioteki DLL. Modułów scalania dla różnych wersji tej samej biblioteki DLL nie można włączyć do jednego instalatora, moduły scalania utrudniają serwisowanie bibliotek DLL niezależnie od aplikacji. Zamiast tego zalecamy zainstalowanie pakietu redystrybucyjnego Visual C++.

## <a name="see-also"></a>Zobacz też

[Ponowne dystrybuowanie plików programu Visual C++](redistributing-visual-cpp-files.md)
