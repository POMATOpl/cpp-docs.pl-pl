---
description: 'Dowiedz się więcej na temat: CWinApp: Klasa aplikacji'
title: 'CWinApp: klasa aplikacji'
ms.date: 11/04/2016
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
ms.openlocfilehash: 63979846ec5b4d5bb5452e98a3ac19474b4fcd0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301636"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: klasa aplikacji

Główna Klasa aplikacji w MFC hermetyzuje inicjalizację, uruchomienie i zakończenie działania aplikacji dla systemu operacyjnego Windows. Aplikacja skompilowana na platformie musi mieć jeden i tylko jeden obiekt klasy pochodzącej od [CWinApp](reference/cwinapp-class.md). Ten obiekt jest konstruowany przed utworzeniem systemu Windows.

`CWinApp` pochodzi od `CWinThread` , który reprezentuje główny wątek wykonania dla aplikacji, co może mieć jeden lub więcej wątków. W ostatnich wersjach MFC `InitInstance` funkcje,, **Run**, `ExitInstance` i `OnIdle` składowe są faktycznie w klasie `CWinThread` . Te funkcje są omawiane w tym miejscu, tak jakby były `CWinApp` elementami członkowskimi, ponieważ dyskusja dotyczy roli obiektu jako obiektu aplikacji, a nie jako wątku podstawowego.

> [!NOTE]
> Klasa aplikacji stanowi podstawowy wątek wykonywania aplikacji. Korzystając z funkcji Win32 API, można również utworzyć pomocnicze wątki wykonywania. Te wątki mogą korzystać z biblioteki MFC. Aby uzyskać więcej informacji, zobacz [wielowątkowość](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Podobnie jak w przypadku każdego programu dla systemu operacyjnego Windows, aplikacja platformy ma `WinMain` funkcję. Jednak w aplikacji platformy nie można pisać `WinMain` . Jest on dostarczany przez bibliotekę klas i jest wywoływany podczas uruchamiania aplikacji. `WinMain` wykonuje standardowe usługi, takie jak rejestrowanie klas okien. Następnie wywołuje funkcje członkowskie obiektu aplikacji w celu zainicjowania i uruchomienia aplikacji. (Można dostosować, `WinMain` zastępując `CWinApp` funkcje członkowskie, które `WinMain` wywołuje.)

Aby zainicjować aplikację, `WinMain` wywołuje funkcje obiektu aplikacji `InitApplication` i `InitInstance` składowe. Aby uruchomić pętlę komunikatów aplikacji, `WinMain` wywołuje funkcję **Uruchom** element członkowski. Po zakończeniu `WinMain` wywoływana jest `ExitInstance` funkcja członkowska obiektu aplikacji.

> [!NOTE]
> Nazwy wyświetlane **pogrubione** w tej dokumentacji wskazują elementy dostarczone przez biblioteka MFC i Visual C++. Nazwy wyświetlane w polu `monospaced` Typ wskazują elementy, które tworzysz lub przesłonisz.

## <a name="see-also"></a>Zobacz też

[Ogólne tematy dotyczące MFC](general-mfc-topics.md)<br/>
[CWinApp i Kreator aplikacji MFC](cwinapp-and-the-mfc-application-wizard.md)<br/>
[CWinApp funkcje członkowskie](overridable-cwinapp-member-functions.md)<br/>
[Specjalne usługi CWinApp](special-cwinapp-services.md)
