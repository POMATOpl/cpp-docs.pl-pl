---
description: 'Dowiedz się więcej na temat: Automatyzacja w bibliotece DLL'
title: Automatyzacja w bibliotece DLL
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: e0d6d0beec71f3994f6e726c6946b2069d1b081b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163239"
---
# <a name="automation-in-a-dll"></a>Automatyzacja w bibliotece DLL

Po wybraniu opcji Automatyzacja w Kreatorze MFC DLL, Kreator udostępnia następujące informacje:

- Język opisu obiektu początkowego (. ODL) — plik

- Dyrektywa include w pliku STDAFX. h dla Afxole. h

- Implementacja `DllGetClassObject` funkcji, która wywołuje funkcję **AfxDllGetClassObject**

- Implementacja `DllCanUnloadNow` funkcji, która wywołuje funkcję **AfxDllCanUnloadNow**

- Implementacja `DllRegisterServer` funkcji, która wywołuje funkcję [COleObjectFactory:: UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall)

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Serwery automatyzacji](../mfc/automation-servers.md)

## <a name="see-also"></a>Zobacz też

[Tworzenie bibliotek DLL C/C++ w programie Visual Studio](dlls-in-visual-cpp.md)
