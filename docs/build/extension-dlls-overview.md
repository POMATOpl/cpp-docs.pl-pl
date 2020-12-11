---
description: 'Dowiedz się więcej na temat: biblioteki DLL rozszerzeń MFC: Omówienie'
title: 'Biblioteki DLL rozszerzeń: omówienie'
ms.date: 05/06/2019
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: b877eeaae2e67466d4b695820659c5718d552d0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162927"
---
# <a name="mfc-extension-dlls-overview"></a>Biblioteki DLL rozszerzeń MFC: Omówienie

Biblioteka DLL rozszerzenia MFC jest biblioteką DLL, która zwykle implementuje klasy wielokrotnego użytku, pochodzące z istniejących klas biblioteka MFC. Biblioteki DLL rozszerzeń MFC są tworzone przy użyciu biblioteki dołączanej dynamicznie MFC (znanej również jako udostępniona wersja MFC). Tylko pliki wykonywalne MFC (aplikacje lub zwykłe biblioteki MFC DLL), które są tworzone przy użyciu udostępnionej wersji MFC, mogą korzystać z biblioteki DLL rozszerzenia MFC. Za pomocą biblioteki MFC DLL rozszerzenia można utworzyć nowe klasy niestandardowe z MFC, a następnie zaoferować tę rozszerzoną wersję MFC do aplikacji, które wywołują bibliotekę DLL.

Rozszerzenia bibliotek DLL mogą być również używane do przekazywania obiektów pochodnych MFC między aplikacją a biblioteką DLL. Funkcje składowe skojarzone z przekazanym obiektem istnieją w module, w którym został utworzony obiekt. Ponieważ te funkcje są prawidłowo eksportowane przy użyciu udostępnionej wersji biblioteki DLL MFC, można swobodne przekazywanie wskaźników obiektów pochodnych MFC lub MFC między aplikacjami i bibliotekami DLL rozszerzenia MFC, które ładuje.

Aby zapoznać się z przykładem biblioteki DLL, która spełnia podstawowe wymagania biblioteki DLL rozszerzenia MFC, zobacz przykład MFC [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). W szczególności zapoznaj się z plikami TESTDLL1. cpp i TESTDLL2. cpp.

## <a name="what-do-you-want-to-do"></a>Co chcesz zrobić?

- [Inicjowanie biblioteki DLL rozszerzenia MFC](run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Biblioteki DLL rozszerzeń MFC](extension-dlls.md)

- [Korzystanie z bibliotek DLL rozszerzeń MFC w bazie danych, OLE i Sockets w zwykłych bibliotekach DLL MFC](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [Biblioteki innego typu niż DLL MFC: Omówienie](non-mfc-dlls-overview.md)

- [Zwykłe biblioteki DLL MFC połączone statycznie z MFC](regular-dlls-statically-linked-to-mfc.md)

- [Zwykłe biblioteki DLL MFC połączone dynamicznie z MFC](regular-dlls-dynamically-linked-to-mfc.md)

- [Tworzenie biblioteki MFC DLL](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>Zobacz też

[Rodzaje bibliotek DLL](kinds-of-dlls.md)
