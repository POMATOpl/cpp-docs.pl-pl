---
description: 'Dowiedz się więcej na temat: testowanie właściwości i zdarzeń za pomocą kontenera testów'
title: Testowanie właściwości i zdarzeń za pomocą kontenera testu
ms.date: 11/04/2016
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
ms.openlocfilehash: 61cccbda723fb1cfac0ca3fc696639849bde9dd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216226"
---
# <a name="testing-properties-and-events-with-test-container"></a>Testowanie właściwości i zdarzeń za pomocą kontenera testu

Aplikacja kontenera testowego, dostarczona w Visual C++, jest kontenerem kontrolki ActiveX do testowania i debugowania formantów ActiveX. Kontener testowy umożliwia deweloperowi kontroli przetestowanie funkcjonalności kontrolki przez zmianę jej właściwości, wywołanie jej metod i wyzwolenie jej zdarzeń. Kontener testowy może wyświetlać dzienniki powiadomień o powiązaniach danych, a także funkcje do testowania trwałości kontrolki ActiveX: można zapisać właściwości do strumienia lub do magazynu, załadować je ponownie i sprawdzić zapisane dane strumienia. W tej sekcji opisano sposób korzystania z podstawowych funkcji kontenera testowego. Aby uzyskać dodatkowe informacje, wybierz menu **Pomoc** podczas uruchamiania kontenera testowego.

### <a name="to-access-the-activex-control-test-container"></a>Aby uzyskać dostęp do kontenera testów kontrolki ActiveX

1. Kompiluj [przykład TSTCON: kontener testów kontrolki ActiveX](../overview/visual-cpp-samples.md).

### <a name="to-test-your-activex-control"></a>Aby przetestować formant ActiveX

1. W menu **Edycja** kontenera testowego kliknij polecenie **Wstaw nową kontrolkę**.

1. W polu **kontrolka Wstaw** zaznacz żądany formant i kliknij przycisk **OK**. Kontrolka zostanie wyświetlona w kontenerze sterowania.

    > [!NOTE]
    >  Jeśli formant nie znajduje się na liście w oknie dialogowym **Wstawianie kontrolki** , upewnij się, że zarejestrowano go za pomocą polecenia **zarejestruj formanty** w menu **plik** kontenera testów.

W tym momencie można testować właściwości lub zdarzenia kontrolki.

#### <a name="to-test-properties"></a>Aby przetestować właściwości

1. W menu **sterowania** kliknij polecenie **wywołaj metody**.

1. Z listy rozwijanej **Nazwa metody** wybierz metodę propput dla właściwości, która ma zostać przetestowana.

1. Zmodyfikuj **wartość parametru** lub **Typ parametru** , a następnie kliknij przycisk **Ustaw wartość** .

1. Kliknij pozycję **Wywołaj** , aby zastosować nową wartość do obiektu.

   Właściwość zawiera teraz nową wartość.

#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>Aby przetestować zdarzenia i określić miejsce docelowe informacji o zdarzeniu.

1. W menu **Opcje** kliknij pozycję **Rejestrowanie**.

1. Określ miejsce docelowe informacji o zdarzeniu.

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC](../mfc/mfc-activex-controls.md)<br/>
[Instrukcje: debugowanie kontrolki ActiveX](/visualstudio/debugger/how-to-debug-an-activex-control)
