---
description: 'Dowiedz się więcej o: kontrolki ActiveX MFC: używanie stron właściwości podstawowych'
title: 'Kontrolki ActiveX MFC: używanie stron właściwości standardowych'
ms.date: 09/12/2018
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
ms.openlocfilehash: 37cb6e5b5dfa08c5e7935064a66c2c77fe8dcde6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133058"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>Kontrolki ActiveX MFC: używanie stron właściwości standardowych

W tym artykule omówiono strony właściwości giełdowe dostępne dla formantów ActiveX i sposobu ich używania.

>[!IMPORTANT]
> Kontrolka ActiveX to Starsza technologia, która nie powinna być używana do nowych celów programistycznych. Aby uzyskać więcej informacji na temat nowoczesnych technologii, które zastępują ActiveX, zobacz [kontrolki ActiveX](activex-controls.md).

Aby uzyskać więcej informacji na temat używania stron właściwości w kontrolce ActiveX, zobacz następujące artykuły:

- [Kontrolki ActiveX MFC: strony właściwości](mfc-activex-controls-property-pages.md)

- [Kontrolki ActiveX MFC: Dodawanie innej niestandardowej strony właściwości](mfc-activex-controls-adding-another-custom-property-page.md)

MFC udostępnia trzy strony właściwości podstawowych do użycia z kontrolkami ActiveX: `CLSID_CColorPropPage` , `CLSID_CFontPropPage` , i `CLSID_CPicturePropPage` . Te strony zawierają odpowiednio interfejs użytkownika dla koloru, czcionki i właściwości obrazu.

Aby dołączyć te strony właściwości do kontrolki, Dodaj ich identyfikatory do kodu, który inicjuje tablicę identyfikatorów stron właściwości formantu. W poniższym przykładzie kod ten znajduje się w pliku implementacji kontroli (. CPP) Inicjuje tablicę zawierającą wszystkie trzy strony właściwości podstawowych i domyślną stronę właściwości (o nazwie `CMyPropPage` w tym przykładzie):

[!code-cpp[NVC_MFC_AxOpt#21](codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

Należy zauważyć, że liczba stron właściwości w makrze BEGIN_PROPPAGEIDS, wynosi 4. Przedstawia liczbę stron właściwości obsługiwanych przez formant ActiveX.

Po dokonaniu tych modyfikacji ponownie skompiluj projekt. Kontrolka ma teraz strony właściwości dla właściwości font, Picture i Color.

> [!NOTE]
> Jeśli nie można uzyskać dostępu do stron właściwości kontroli, może to być spowodowane tym, że biblioteka MFC DLL (MFCxx.DLL) nie została prawidłowo zarejestrowana w bieżącym systemie operacyjnym. Zazwyczaj wynika to z instalacji Visual C++ w systemie operacyjnym innym niż aktualnie uruchomiony.

> [!TIP]
> Jeśli strony właściwości podstawowych nie są widoczne (zobacz poprzednią uwagę), zarejestruj bibliotekę DLL, uruchamiając RegSvr32.exe z wiersza polecenia z pełną nazwą ścieżki do biblioteki DLL.

## <a name="see-also"></a>Zobacz też

[Kontrolki ActiveX MFC](mfc-activex-controls.md)<br/>
[Kontrolki ActiveX MFC: Dodawanie właściwości podstawowych](mfc-activex-controls-adding-stock-properties.md)
