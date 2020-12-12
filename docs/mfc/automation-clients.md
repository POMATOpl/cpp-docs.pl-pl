---
description: 'Dowiedz się więcej na temat: Klienci automatyzacji'
title: Klienci automatyzacji
ms.date: 11/04/2016
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
ms.openlocfilehash: 38379feb0881b154418daa5c02980eeee2dd21e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273959"
---
# <a name="automation-clients"></a>Klienci automatyzacji

Automatyzacja pozwala aplikacji na manipulowanie obiektami zaimplementowanymi w innej aplikacji lub Uwidacznianie obiektów, aby można było manipulować nimi. Klient usługi Automation to aplikacja, która może manipulować uwidocznionymi obiektami należącymi do innej aplikacji. Aplikacja, która uwidacznia obiekty, jest nazywana serwerem automatyzacji. Klient manipuluje obiektami aplikacji serwera, uzyskując dostęp do tych obiektów i właściwości.

### <a name="types-of-automation-clients"></a>Typy klientów automatyzacji

Istnieją dwa typy klientów automatyzacji:

- Klienci, którzy dynamicznie (w czasie wykonywania) uzyskują informacje o właściwościach i operacjach serwera.

- Klienci, którzy posiadają informacje statyczne (dostarczane w czasie kompilacji), które określają właściwości i operacje serwera.

Klienci pierwszego rodzaju uzyskują informacje o metodach i właściwościach serwera, wykonując zapytania o mechanizm systemu OLE `IDispatch` . Chociaż jest to wystarczające do użycia w przypadku klientów dynamicznych, `IDispatch` trudno jest używać w przypadku klientów statycznych, w których obiekty muszą być znane w czasie kompilacji. W przypadku klientów z ograniczeniami statycznymi klasy programu Microsoft Foundation dostarczają klasy [COleDispatchDriver](reference/coledispatchdriver-class.md) .

Klienci z granicami statycznymi używają klasy proxy, która jest statycznie połączona z aplikacją kliencką. Ta klasa zapewnia bezpieczny typ hermetyzacji języka C++ właściwości i operacji aplikacji serwera.

Klasa `COleDispatchDriver` zapewnia główną pomoc techniczną po stronie klienta automatyzacji. Za pomocą okna dialogowego **Dodawanie nowego elementu** utworzysz klasę pochodną `COleDispatchDriver` .

Następnie należy określić plik biblioteki typów opisujący właściwości i funkcje obiektu aplikacji serwera. Okno dialogowe Dodawanie elementu odczytuje ten plik i tworzy `COleDispatchDriver` klasę pochodną, z funkcjami składowymi, które aplikacja może wywołać, aby uzyskać dostęp do obiektów aplikacji serwera w języku C++ w sposób bezpieczny dla typów. Dodatkowe funkcje dziedziczone przez `COleDispatchDriver` upraszczają proces wywoływania odpowiedniego serwera automatyzacji.

### <a name="handling-events-in-automation-clients"></a>Obsługa zdarzeń w klientach automatyzacji

Jeśli chcesz obsługiwać zdarzenia w kliencie usługi Automation, musisz dodać interfejs ujścia. MFC zapewnia obsługę kreatora, aby dodać interfejsy ujścia dla formantów ActiveX, ale nie obsługuje innych serwerów COM.

## <a name="see-also"></a>Zobacz też

[Klienci automatyzacji: korzystanie z bibliotek typów](automation-clients-using-type-libraries.md)<br/>
[Automatyzacja](automation.md)<br/>
[Kreator aplikacji MFC](reference/mfc-application-wizard.md)
