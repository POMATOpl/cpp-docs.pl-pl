---
description: 'Dowiedz się więcej o: funkcja członkowska InitInstance'
title: InitInstance — Funkcja członkowska
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: b55c5dbd665b45c74e5990b7d40a63fcd9098a9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220620"
---
# <a name="initinstance-member-function"></a>InitInstance — Funkcja członkowska

System operacyjny Windows pozwala uruchamiać więcej niż jedną kopię lub "wystąpienie" tej samej aplikacji. `WinMain` wywołuje [InitInstance](reference/cwinapp-class.md#initinstance) za każdym razem, gdy zostanie uruchomione nowe wystąpienie aplikacji.

Standardowa `InitInstance` implementacja utworzona przez Kreatora aplikacji MFC wykonuje następujące zadania:

- Jako centralna akcja tworzy szablony dokumentów, które z kolei umożliwiają tworzenie dokumentów, widoków i okien ramowych. Opis tego procesu można znaleźć w temacie [Tworzenie szablonu dokumentu](document-template-creation.md).

- Ładuje standardowe opcje plików z pliku. ini lub rejestru systemu Windows, łącznie z nazwami ostatnio używanych plików.

- Rejestruje jeden lub więcej szablonów dokumentów.

- W przypadku aplikacji MDI program tworzy okno głównej ramki.

- Przetwarza wiersz polecenia, aby otworzyć dokument określony w wierszu polecenia lub otworzyć nowy pusty dokument.

Możesz dodać własny kod inicjalizacji lub zmodyfikować kod zapisany przez kreatora.

> [!NOTE]
> Aplikacje MFC muszą być zainicjowane jako Apartament jednowątkowy (STA). Jeśli wywołasz [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) w `InitInstance` przesłonięciu, określ COINIT_APARTMENTTHREADED (a nie COINIT_MULTITHREADED).

## <a name="see-also"></a>Zobacz też

[CWinApp: Klasa aplikacji](cwinapp-the-application-class.md)
