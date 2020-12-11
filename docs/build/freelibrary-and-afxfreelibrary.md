---
description: 'Dowiedz się więcej na temat: FreeLibrary i AfxFreeLibrary'
title: FreeLibrary i AfxFreeLibrary
ms.date: 11/04/2016
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
ms.openlocfilehash: ea4da8c69aa663add85e740d99b68731e263b442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162797"
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary i AfxFreeLibrary

Procesy, które jawnie łączą się z biblioteką DLL, wywołują funkcję [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) , gdy moduł dll nie jest już wymagany. Ta funkcja zmniejsza liczbę odwołań modułu. A jeśli licznik odwołań ma wartość zero, nie jest mapowany z przestrzeni adresowej procesu.

W aplikacji MFC Użyj [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) zamiast, `FreeLibrary` Aby zwolnić bibliotekę DLL rozszerzenia MFC. Interfejs (prototyp funkcji) dla `AfxFreeLibrary` jest taki sam jak `FreeLibrary` .

## <a name="what-do-you-want-to-do"></a>Co chcesz zrobić?

- [Łączenie pliku wykonywalnego z biblioteką DLL](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Łączenie pliku wykonywalnego z biblioteką DLL](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [LoadLibrary i AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>Zobacz też

[Tworzenie bibliotek DLL C/C++ w programie Visual Studio](dlls-in-visual-cpp.md)\
[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)\
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
