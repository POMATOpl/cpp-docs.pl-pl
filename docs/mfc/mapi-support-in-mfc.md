---
description: Dowiedz się więcej o obsłudze MAPI w MFC
title: Obsługa MAPI w MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
ms.openlocfilehash: 289ad61894efd5c08d3a50d8c50e3ac6ee518a25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280758"
---
# <a name="mapi-support-in-mfc"></a>Obsługa MAPI w MFC

MFC udostępnia obsługę podzestawu interfejsu programu Microsoft Messaging Application Program (MAPI) w klasie `CDocument` . W `CDocument` związku z tym program ma funkcje członkowskie, które określają, czy obsługa poczty jest obecna na komputerze użytkownika końcowego, a jeśli tak, należy włączyć polecenie Wyślij pocztą e-mail, którego identyfikator polecenia standardowego jest ID_FILE_SEND_MAIL. Funkcja obsługi MFC dla tego polecenia umożliwia użytkownikowi Wysyłanie dokumentu pocztą elektroniczną.

> [!TIP]
> Chociaż MFC nie hermetyzuje całego zestawu funkcji MAPI, można nadal wywoływać funkcje MAPI bezpośrednio, podobnie jak można wywoływać Win32 API funkcje bezpośrednio z programów MFC.

Udostępnianie polecenia Wyślij pocztę w aplikacji jest bardzo proste. MFC udostępnia implementację dokumentu (czyli `CDocument` obiekt pochodny) jako załącznik i wyślij ją jako wiadomość e-mail. Ten załącznik jest równoznaczny z poleceniem Zapisz plik, które zapisuje (serializować) zawartość dokumentu w wiadomości e-mail. Ta implementacja wywołuje klienta poczty na komputerze użytkownika w celu nadania użytkownikowi możliwości adresowania wiadomości e-mail i dodania tematu i tekstu wiadomości do wiadomości e-mail. Użytkownicy widzą interfejs użytkownika znanej aplikacji poczty. Ta funkcja jest dostarczana przez dwie `CDocument` funkcje składowe: `OnFileSendMail` i `OnUpdateFileSendMail` .

Interfejs MAPI musi odczytać plik w celu wysłania załącznika. Jeśli aplikacja utrzymuje plik danych otwarty podczas `OnFileSendMail` wywołania funkcji, należy otworzyć plik z trybem udostępniania, który umożliwia wielu procesom dostęp do pliku.

> [!NOTE]
> Zastępowanie wersji `OnFileSendMail` dla klasy `COleDocument` prawidłowo obsługuje dokumenty złożone.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>Aby zaimplementować polecenie wysyłania poczty z MFC

1. Użyj edytora menu Visual C++, aby dodać element menu, którego identyfikator polecenia jest ID_FILE_SEND_MAIL.

   Ten identyfikator polecenia jest dostarczany przez strukturę w plik AFXRES. H. Polecenie można dodać do dowolnego menu, ale jest zazwyczaj dodawane do menu **plik** .

1. Dodaj ręcznie następujący element do mapy komunikatów dokumentu:

   [!code-cpp[NVC_MFCDocView#9](codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Ta mapa komunikatów działa w przypadku dokumentu pochodzącego z albo `CDocument` lub — pobiera w `COleDocument` obu przypadkach poprawną klasę bazową, mimo że mapa wiadomości znajduje się w klasie dokumentu pochodnego.

1. Kompiluj aplikację.

Jeśli obsługa poczty jest dostępna, MFC włącza element menu za pomocą `OnUpdateFileSendMail` polecenia, a następnie przetwarza je w programie `OnFileSendMail` . Jeśli obsługa poczty jest niedostępna, MFC automatycznie usuwa element menu, dzięki czemu użytkownik nie zobaczy tego elementu.

> [!TIP]
> Zamiast ręcznego dodawania wpisów mapy komunikatów, jak opisano wcześniej, można użyć [kreatora klas](reference/mfc-class-wizard.md) klas do mapowania komunikatów do funkcji. Aby uzyskać więcej informacji, zobacz [Mapowanie komunikatów do funkcji](reference/mapping-messages-to-functions.md).

Aby uzyskać powiązane informacje, zobacz Omówienie [MAPI](mapi.md) .

Aby uzyskać więcej informacji na temat `CDocument` funkcji Członkowskich, które umożliwiają korzystanie z MAPI, zobacz:

- [CDocument:: OnFileSendMail](reference/cdocument-class.md#onfilesendmail)

- [CDocument:: OnUpdateFileSendMail](reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>Zobacz też

[MAPI](mapi.md)
