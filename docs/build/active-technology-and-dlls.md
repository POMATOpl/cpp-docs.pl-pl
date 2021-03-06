---
description: 'Dowiedz się więcej na temat: Technologia Active i biblioteki DLL'
title: Technologia Active i biblioteki DLL
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: 02a11bd18e8c6f62748d0be3f4cd708c8e4e4621
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157142"
---
# <a name="active-technology-and-dlls"></a>Technologia Active i biblioteki DLL

Technologia Active umożliwia całkowite wdrożenie serwerów obiektów wewnątrz biblioteki DLL. Ten typ serwera jest nazywany serwerem w procesie. MFC nie obsługuje w pełni skalowalnych serwerów dla wszystkich funkcji edycji wizualizacji, głównie ponieważ technologia Active nie umożliwia serwerowi podłączania do głównej pętli komunikatów kontenera. MFC wymaga dostępu do pętli komunikatów aplikacji kontenera w celu obsługi kluczy akceleratora i przetwarzania w czasie bezczynności.

Jeśli piszesz serwer automatyzacji, a serwer nie ma interfejsu użytkownika, możesz utworzyć serwer na serwerze i umieścić go w całości w bibliotece DLL.

## <a name="what-do-you-want-to-know-more-about"></a>Jak chcesz dowiedzieć się więcej?

- [Serwery automatyzacji](../mfc/automation-servers.md)

## <a name="see-also"></a>Zobacz też

[Tworzenie bibliotek DLL C/C++ w programie Visual Studio](dlls-in-visual-cpp.md)
