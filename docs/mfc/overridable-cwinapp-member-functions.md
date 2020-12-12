---
description: 'Dowiedz się więcej na temat: Zastąp funkcje członkowskie CWinApp'
title: Funkcje członkowskie CWinApp z możliwością zastąpienia
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 3958ad0edc1fbdb77e1f6ce3252fd03d7595344a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330098"
---
# <a name="overridable-cwinapp-member-functions"></a>Funkcje członkowskie CWinApp z możliwością zastąpienia

[CWinApp](reference/cwinapp-class.md) udostępnia kilka kluczowych funkcji Członkowskich ( `CWinApp` zastępuje te elementy z klasy [CWinThread](reference/cwinthread-class.md), z których `CWinApp` wynika):

- [InitInstance](initinstance-member-function.md)

- [Uruchom](run-member-function.md)

- [ExitInstance](exitinstance-member-function.md)

- [OnIdle](onidle-member-function.md)

Jedyną `CWinApp` funkcją członkowską, którą należy przesłonić, jest `InitInstance` .

## <a name="see-also"></a>Zobacz też

[CWinApp: Klasa aplikacji](cwinapp-the-application-class.md)
