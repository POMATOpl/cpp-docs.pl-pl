---
description: 'Dowiedz się więcej o: zapewnianie aktywacji bez okien'
title: Zapewnianie aktywacji niepowiązanej z oknami
ms.date: 11/04/2016
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
ms.openlocfilehash: ea9b86c977926e57bd3593ec861498eb5d909f37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248635"
---
# <a name="providing-windowless-activation"></a>Zapewnianie aktywacji niepowiązanej z oknami

Kod tworzenia okna (czyli wszystko, co się dzieje po wywołaniu `CreateWindow` ) jest kosztowny do wykonania. Kontrolka, która utrzymuje okno na ekranie, musi zarządzać komunikatami dla tego okna. Kontrolki bez okien są z tego powodu szybsze niż kontrolki z systemem Windows.

Dodatkowa zaletą formantów bez okien jest to, w przeciwieństwie do kontrolek okienkowych, kontrolki bez okien obsługują przezroczyste malowanie i nieprostokątne regiony ekranu. Typowym przykładem przezroczystej kontrolki jest kontrolka tekstowa z przezroczystym tłem. Kontrolki malują tekst, ale nie w tle, więc w dowolnym obszarze tekstu jest wyświetlany tekst. Nowsze formularze często wykorzystują kontrolki nieprostokątne, takie jak strzałki i okrągłe przyciski.

Często formant nie musi mieć własnego okna, a zamiast tego może korzystać z usług systemu Windows jego kontenera, pod warunkiem, że kontener został zapisany do obsługi obiektów bez okien. Kontrolki bez okien są zgodne z poprzednimi kontenerami. W starszych kontenerach, które nie są zapisywane do obsługi kontrolek bez okien, formanty bez okien tworzą okno, gdy aktywne.

Ponieważ kontrolki bez okien nie mają własnych okien, kontener (z oknem) jest odpowiedzialny za świadczenie usług, które w przeciwnym razie byłyby udostępniane przez własne okno kontrolki. Na przykład, Jeśli kontrolka musi zbadać fokus klawiatury, przechwycić mysz lub uzyskać kontekst urządzenia, te operacje są zarządzane przez kontener. Kontener kieruje komunikaty wejściowe użytkownika wysyłane do okna do odpowiedniej kontrolki bez okna przy użyciu `IOleInPlaceObjectWindowless` interfejsu. (Zobacz *zestaw SDK ActiveX* , aby uzyskać opis tego interfejsu). `COleControl` funkcje członkowskie wywołują te usługi z kontenera.

Aby formant używał bezokienkowej aktywacji, należy uwzględnić flagę **windowlessActivate** w zestawie flag zwracanych przez [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Na przykład:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]

Kod do uwzględnienia tej flagi jest generowany automatycznie po wybraniu opcji **Aktywacja bez okien** na stronie [Ustawienia kontrolki](../mfc/reference/control-settings-mfc-activex-control-wizard.md) kreatora kontrolek ActiveX MFC.

Gdy Aktywacja bez okien jest włączona, kontener przekaże komunikaty wejściowe do interfejsu kontrolki `IOleInPlaceObjectWindowless` . `COleControl`implementacja tego interfejsu wysyła komunikaty za pomocą mapy komunikatów kontrolki, po dopasowaniu odpowiednio współrzędnych myszy. Komunikaty, takie jak zwykłe komunikaty okna, można przetwarzać przez dodanie odpowiednich wpisów do mapy komunikatów. W przypadku obsługi tych komunikatów należy unikać używania *m_hWnd* zmiennej składowej (lub żadnej funkcji składowej, która go używa) bez uprzedniego sprawdzenia, czy jej wartość nie jest **równa null**.

`COleControl` Program udostępnia funkcje członkowskie, które wywołują funkcję przechwytywania myszy, fokus klawiatury, przewijanie i inne usługi okna z kontenera, w tym:

- [GetFocus](../mfc/reference/colecontrol-class.md#getfocus), [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)

- [Getcapture](../mfc/reference/colecontrol-class.md#getcapture), [setcapture](../mfc/reference/colecontrol-class.md#setcapture), [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)

- [GetDC —](../mfc/reference/colecontrol-class.md#getdc), [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)

- [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)

- [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)

- [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)

W kontrolkach bez okien należy zawsze używać `COleControl` funkcji składowych zamiast odpowiednich `CWnd` funkcji składowych lub powiązanych z nimi funkcji Win32 API.

Możesz chcieć, aby kontrolka bez okien była elementem docelowym operacji przeciągania i upuszczania OLE. Zwykle jest to wymagane, aby okno kontrolki było rejestrowane jako miejsce docelowe upuszczania. Ponieważ kontrolka nie ma własnego okna, kontener używa własnego okna jako elementu docelowego upuszczania. Formant zawiera implementację `IDropTarget` interfejsu, do którego kontener może delegować wywołania w odpowiednim czasie. Aby udostępnić ten interfejs do kontenera, Zastąp [COleControl:: GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget). Na przykład:

[!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC: Optymalizacja](../mfc/mfc-activex-controls-optimization.md)
