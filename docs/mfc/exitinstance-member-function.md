---
description: 'Dowiedz się więcej o: funkcja członkowska ExitInstance'
title: ExitInstance — Funkcja członkowska
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: a469d29c6b8dc2b822928293ee3bd083ccce95e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314727"
---
# <a name="exitinstance-member-function"></a>ExitInstance — Funkcja członkowska

Funkcja członkowska [ExitInstance](reference/cwinapp-class.md#exitinstance) klasy [CWinApp](reference/cwinapp-class.md) jest wywoływana za każdym razem, gdy kopia aplikacji zostanie zakończona, zazwyczaj w wyniku zamknięcia aplikacji.

Zastąp `ExitInstance` , jeśli wymagane jest specjalne oczyszczanie, np. zwalnianie zasobów interfejsu urządzenia graficznego (GDI) lub cofanie alokacji pamięci używanej podczas wykonywania programu. Oczyszczanie elementów standardowych, takich jak dokumenty i widoki, jest jednak dostarczane przez platformę z innymi funkcjami zaszeregowania służącymi do wykonywania specjalnych czynności czyszczących specyficznych dla tych obiektów.

## <a name="see-also"></a>Zobacz też

[CWinApp: Klasa aplikacji](cwinapp-the-application-class.md)
