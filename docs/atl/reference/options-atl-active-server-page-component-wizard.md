---
description: Dowiedz się więcej na temat opcji, Kreator składnika strony Active Server ATL
title: Opcje, Kreator składnika strony Active Server ATL
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.options
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
ms.openlocfilehash: 6d41b5cb43aa9f0445e73bbe148a2a753e374a15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139025"
---
# <a name="options-atl-active-server-page-component-wizard"></a>Opcje, Kreator składnika strony Active Server ATL

Ta strona kreatora wieloskładnikowej strony Active Server ATL służy do projektowania w celu zwiększenia wydajności i błędów dla obiektu.

Aby uzyskać więcej informacji na temat projektów ATL i klas COM ATL, zobacz [składniki komputerów stacjonarnych ATL com](../../atl/atl-com-desktop-components.md).

- **Model wątkowości**

   Wskazuje metodę zarządzania wątkami. Domyślnie projekt używa wątków **apartamentu** .

   Aby uzyskać więcej informacji [, zobacz Określanie modelu wątkowości projektu](../../atl/specifying-the-threading-model-for-a-project-atl.md) .

   |Opcja|Opis|
   |------------|-----------------|
   |**Pojedyncze**|Określa, że obiekt używa modelu jednowątkowego. W modelu pojedynczego wątku obiekt zawsze jest uruchamiany w podstawowym wątku COM. Aby uzyskać więcej informacji, zobacz apartamentach i [InprocServer32](/windows/win32/com/inprocserver32) o [pojedynczym wątku](/windows/win32/com/single-threaded-apartments) .|
   |**Apartamentu**|Określa, że obiekt używa wątka Apartment. Równoważne z pojedynczym apartamentem wątku. Każdy obiekt składnika Apartment jest przypisany do wątku, dla którego jest przeznaczony dla tego obiektu; Jednak wiele wątków może być używanych dla wielu obiektów. Każda komórka jest powiązana z określonym wątkiem i ma pompę komunikatów systemu Windows (domyślnie).<br /><br /> Aby uzyskać więcej informacji, zobacz [apartamentach pojedyncze wątki](/windows/win32/com/single-threaded-apartments) .|
   |**Oba**|Określa, że obiekt może używać Apartment lub Free Threading, w zależności od tego, jaki typ wątku jest tworzony.|
   |**Bezpłatna**|Określa, że obiekt używa wolnych wątków. Bezpłatna wątkowość jest równoważna z modelem apartamentu wielowątkowej. Aby uzyskać więcej informacji, zobacz [wielowątkowy apartamentach](/windows/win32/com/multithreaded-apartments) .|
   |**Zerowy**|Określa, że obiekt jest zgodny z wytycznymi dla wielowątkowych apartamentach, ale można go wykonać na dowolnym rodzaju wątku.|

- **Agregacja**

   Wskazuje, czy obiekt używa [agregacji](/windows/win32/com/aggregation). Obiekt zagregowany wybiera interfejsy, które należy uwidocznić klientom, a interfejsy są ujawniane tak, jakby obiekt agregacji zaimplementował je. Klienci obiektu zagregowanego komunikują się tylko z obiektem Aggregate.

   |Opcja|Opis|
   |------------|-----------------|
   |**Tak**|Określa, że obiekt może być zagregowany. Domyślnie.|
   |**Nie**|Określa, że obiekt nie jest agregowany.|
   |**Jedyn**|Określa, że obiekt musi być zagregowany.|

- **Pomoc techniczna**

   Dodatkowe opcje pomocy technicznej:

   |Opcja|Opis|
   |------------|-----------------|
   |**ISupportErrorInfo**|Tworzy obsługę interfejsu [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) , aby obiekt mógł zwrócić do klienta informacje o błędzie.|
   |**Punkty połączenia**|Włącza punkty połączenia dla obiektu przez uczynienie klasy obiektu pochodną od [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md).|
   |**Organizator wolnych wątków**|Tworzy obiekt organizatora wolnych wątków do wydajnego organizowania wskaźników interfejsów między wątkami w tym samym procesie. Dostępne dla obiektu określającego **oba** lub **wolne** jako model wątkowości.|

## <a name="see-also"></a>Zobacz też

[Kreator składników stron Active Server Page ATL](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[Składnik strony Active Server ATL](../../atl/reference/adding-an-atl-active-server-page-component.md)
