---
description: 'Dowiedz się więcej o: obsługa kontekstów aktywacji w stanie modułu MFC'
title: Obsługa kontekstów aktywacji w stanie modułu MFC
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: e7f7434824956ca2a62d75fbd50eb9dd5e01f34e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216473"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Obsługa kontekstów aktywacji w stanie modułu MFC

MFC tworzy kontekst aktywacji przy użyciu zasobu manifestu dostarczonego przez moduł użytkownika. Aby uzyskać więcej informacji na temat tworzenia kontekstów aktywacji, zobacz następujące tematy:

- [Konteksty aktywacji](/windows/win32/SbsCs/activation-contexts)

- [Manifesty aplikacji](/windows/win32/SbsCs/application-manifests)

- [Manifesty zestawu](/windows/win32/SbsCs/assembly-manifests)

## <a name="remarks"></a>Uwagi

Podczas odczytywania tych Windows SDK tematów należy zauważyć, że mechanizm kontekstu aktywacji MFC przypomina kontekst aktywacji Windows SDK, z wyjątkiem tego, że MFC nie używa interfejsu API kontekstu aktywacji Windows SDK.

Kontekst aktywacji działa w aplikacjach MFC, bibliotekach DLL użytkownika i bibliotekach DLL rozszerzenia MFC w następujący sposób:

- Aplikacje MFC używają zasobu o IDENTYFIKATORze 1 dla swojego zasobu manifestu. W takim przypadku MFC nie tworzy własnego kontekstu aktywacji, ale używa domyślnego kontekstu aplikacji.

- Biblioteki DLL użytkownika MFC używają zasobu o IDENTYFIKATORze 2 dla zasobu manifestu. W tym miejscu MFC tworzy kontekst aktywacji dla każdej biblioteki DLL użytkownika, więc różne biblioteki DLL użytkownika mogą korzystać z różnych wersji tych samych bibliotek (na przykład biblioteki wspólnych kontrolek).

- Biblioteki DLL rozszerzeń MFC są zależne od ich aplikacji obsługujących lub bibliotek DLL użytkownika w celu ustalenia ich kontekstu aktywacji.

Mimo że stan kontekstu aktywacji można zmodyfikować przy użyciu procesów opisanych w sekcji [Korzystanie z interfejsu API kontekstu](/windows/win32/SbsCs/using-the-activation-context-api)aktywacji, przy użyciu mechanizmu kontekstu aktywacji MFC może być przydatne podczas opracowywania opartych na bibliotece DLL architektur wtyczek, gdzie nie jest to łatwe (lub niemożliwe) do ręcznego przełączania stanu aktywacji przed i po poszczególnych wywołaniach zewnętrznych.

Kontekst aktywacji jest tworzony w [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit). Jest zniszczony w `AFX_MODULE_STATE` destruktorze. Dojście kontekstu aktywacji jest przechowywane w `AFX_MODULE_STATE` . ( `AFX_MODULE_STATE` został opisany w [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)).

Makro [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) aktywuje i dezaktywuje kontekst aktywacji. `AFX_MANAGE_STATE` włączono obsługę statycznych bibliotek MFC, a także bibliotek MFC DLL, aby umożliwić wykonywanie kodu MFC w odpowiednim kontekście aktywacji wybranym przez użytkownika DLL.

## <a name="see-also"></a>Zobacz też

[Konteksty aktywacji](/windows/win32/SbsCs/activation-contexts)<br/>
[Manifesty aplikacji](/windows/win32/SbsCs/application-manifests)<br/>
[Manifesty zestawu](/windows/win32/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
