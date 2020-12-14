---
description: 'Dowiedz się więcej na temat: Dodawanie klasy MFC z biblioteki typów'
title: Dodawanie klasy MFC z biblioteki typów
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: b5a9979e2581eb3a560736c57c4b1eac4a7e1e81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248375"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Dodawanie klasy MFC z biblioteki typów

Ten Kreator służy do tworzenia klasy MFC z interfejsu w dostępnej bibliotece typów. Można dodać klasę MFC do [aplikacji MFC](../../mfc/reference/creating-an-mfc-application.md), [biblioteki MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)lub [kontrolki ActiveX MFC](../../mfc/reference/creating-an-mfc-activex-control.md).

> [!NOTE]
> Nie trzeba tworzyć projektu MFC z włączonym automatyzacją, aby dodać klasę z biblioteki typów.

Biblioteka typów zawiera binarny opis interfejsów uwidocznionych przez składnik, definiując metody wraz z ich parametrami i zwracanymi typami. Twoja biblioteka typów musi być zarejestrowana do wyświetlania na liście **dostępne biblioteki typów** w Kreatorze dodawania klasy z biblioteki typów.

### <a name="to-add-an-mfc-class-from-a-type-library"></a>Aby dodać klasę MFC z biblioteki typów

1. W **Eksplorator rozwiązań** lub [Widok klasy](/visualstudio/ide/viewing-the-structure-of-code), kliknij prawym przyciskiem myszy nazwę projektu, do którego chcesz dodać klasę.

1. W menu skrótów kliknij polecenie **Dodaj**, a następnie kliknij przycisk **Dodaj klasę**.

1. W oknie dialogowym [Dodawanie klasy](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) w okienku Szablony kliknij pozycję **Klasa MFC z biblioteki typów**, a następnie kliknij przycisk **Otwórz** , aby wyświetlić [Kreatora dodawania klasy z biblioteki typów](../../mfc/reference/add-class-from-typelib-wizard.md).

W kreatorze można dodać więcej niż jedną klasę w bibliotece typów. Podobnie można dodać klasy z więcej niż jednej biblioteki typów w pojedynczej sesji kreatora.

Kreator tworzy klasę MFC, pochodną od [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), dla każdego dodawanego interfejsu z wybranej biblioteki typów. `COleDispatchDriver` implementuje po stronie klienta Automatyzacja OLE.

## <a name="see-also"></a>Zobacz też

[Klienci automatyzacji](../../mfc/automation-clients.md)<br/>
[Klienci automatyzacji: korzystanie z bibliotek typów](../../mfc/automation-clients-using-type-libraries.md)
