---
description: 'Dowiedz się więcej o: Sekwencja operacji tworzenia kontrolek ActiveX'
title: Sekwencja operacji przy tworzeniu kontrolek ActiveX
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
ms.openlocfilehash: 15b81716f5feee4dfd4d0ebf47ee4d0d648c4536
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217631"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>Sekwencja operacji przy tworzeniu kontrolek ActiveX

W poniższej tabeli przedstawiono rolę i rolę struktury w tworzeniu kontrolek ActiveX (wcześniej znanych jako formanty OLE).

### <a name="creating-activex-controls"></a>Tworzenie kontrolek ActiveX

|Zadanie|Masz|Struktura wykonuje|
|----------|------------|------------------------|
|Utwórz strukturę formantu ActiveX.|Uruchom Kreatora kontrolek ActiveX MFC, aby utworzyć formant. Określ odpowiednie opcje na stronach opcji. Opcje obejmują typ i nazwę formantu w metodzie projektu, licencjonowania, podklasy i pola informacje.|Kreator kontrolek ActiveX MFC tworzy pliki dla kontrolki ActiveX z funkcjonalnością podstawową, w tym pliki źródłowe dla aplikacji, kontrolki i strony właściwości. plik zasobów; plik projektu; i inne, które są dostosowane do Twoich specyfikacji.|
|Zobacz, co oferuje formant i Kreator kontrolek ActiveX, bez dodawania wiersza własnego kodu.|Utwórz formant ActiveX i przetestuj go za pomocą programu Internet Explorer lub [przykładu TSTCON](../overview/visual-cpp-samples.md).|Z działającą kontrolką można zmienić rozmiar i przenieść ją. Ma także metodę **about Box** (jeśli została wybrana), która może być wywoływana.|
|Zaimplementuj metody i właściwości formantu.|Zaimplementuj metody i właściwości specyficzne dla kontrolki, dodając funkcje elementów członkowskich, aby zapewnić uwidoczniony interfejs do danych formantu. Dodaj Zmienne Członkowskie, aby przechowywać struktury danych i używać programów obsługi zdarzeń do uruchamiania zdarzeń po określeniu.|Platforma ma już zdefiniowaną mapę do obsługi zdarzeń, właściwości i metod kontrolki, co pozwala skupić się na sposobie implementacji właściwości i metod. Domyślna strona właściwości jest wyświetlana i jest dostarczana domyślna metoda Box o.|
|Konstruowanie strony właściwości lub strony kontrolki.|Użyj edytorów zasobów Visual C++, aby wizualnie edytować interfejs strony właściwości kontrolki:<br /><br />— Tworzenie dodatkowych stron właściwości.<br />— Tworzenie i edytowanie map bitowych, ikon i kursorów.<br /><br /> Możesz również testować strony właściwości w edytorze okien dialogowych.|Domyślny plik zasobów utworzony przez Kreatora aplikacji MFC dostarcza wiele potrzebnych zasobów. Visual C++ umożliwia edytowanie istniejących zasobów i łatwe dodawanie nowych zasobów.|
|Przetestuj zdarzenia, metody i właściwości kontrolki.|Skompiluj ponownie formant i Użyj kontenera testowego, aby sprawdzić, czy programy obsługi działają prawidłowo.|Można wywołać metody kontrolki i manipulować swoimi właściwościami za pomocą interfejsu strony właściwości lub kontenera testowego. Ponadto kontener testowy służy do śledzenia zdarzeń wyzwalanych z kontrolki i powiadomień odebranych przez kontener formantu.|

## <a name="see-also"></a>Zobacz też

[Kompilowanie na platformie](../mfc/building-on-the-framework.md)<br/>
[Sekwencja operacji do kompilowania aplikacji MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[Sekwencja operacji na potrzeby tworzenia aplikacji OLE](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[Sekwencja operacji związanych z tworzeniem aplikacji bazy danych](../mfc/sequence-of-operations-for-creating-database-applications.md)
