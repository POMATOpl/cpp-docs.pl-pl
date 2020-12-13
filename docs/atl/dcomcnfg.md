---
description: 'Dowiedz się więcej o: DCOMCNFG'
title: DCOMCNFG
ms.date: 11/04/2016
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
ms.openlocfilehash: d99b0018d63cedbccaf57ec4cadeb649f390dcf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153164"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG to narzędzie systemu Windows NT 4,0, które pozwala skonfigurować różne ustawienia specyficzne dla modelu DCOM w rejestrze. Okno DCOMCNFG ma trzy strony: domyślne ustawienia zabezpieczeń, domyślne właściwości i aplikacje. W obszarze systemu Windows 2000 znajduje się na czwartej stronie są obecne domyślne protokoły.

## <a name="default-security-page"></a>Domyślna strona zabezpieczeń

Możesz użyć domyślnej strony zabezpieczenia, aby określić domyślne uprawnienia dla obiektów w systemie. Domyślna strona zabezpieczeń ma trzy sekcje: dostęp, uruchamianie i konfiguracja. Aby zmienić wartości domyślne sekcji, kliknij odpowiedni przycisk **Edytuj domyślne** . Te domyślne ustawienia zabezpieczeń są przechowywane w rejestrze w sekcji `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE` .

## <a name="default-protocols-page"></a>Strona protokoły domyślne

Na tej stronie znajduje się zestaw protokołów sieciowych dostępnych dla modelu DCOM na tym komputerze. Zamówienie odzwierciedla priorytet, w którym będą używane; pierwszy na liście ma najwyższy priorytet. Protokoły mogą być dodawane lub usuwane z tej strony.

## <a name="default-properties-page"></a>Domyślna strona właściwości

Na stronie właściwości domyślne należy zaznaczyć pole wyboru **Włącz rozproszony model com na tym komputerze** , jeśli chcesz, aby klienci na innych komputerach mogli uzyskiwać dostęp do obiektów com uruchomionych na tej maszynie. Wybranie tej opcji powoduje ustawienie `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` wartości `Y` .

## <a name="applications-page"></a>Strona aplikacji

Ustawienia dla określonego obiektu można zmienić na stronie aplikacje. Po prostu wybierz aplikację z listy, a następnie kliknij przycisk **Właściwości** . Okno Właściwości ma pięć stron:

- Strona ogólne potwierdza aplikację, z którą pracujesz.

- Strona lokalizacja pozwala określić, gdzie aplikacja ma być uruchamiana, gdy klient wywołuje `CoCreateInstance` odpowiednie identyfikatory CLSID. W przypadku wybrania pola wyboru **Uruchom aplikację na następującym komputerze** , a następnie wprowadź nazwę komputera, `RemoteServerName` wartość zostanie dodana w ramach identyfikatora AppID dla tej aplikacji. Wyczyść pole wyboru **Uruchom aplikację na tym komputerze** `LocalService` , aby ponownie nazwać wartość do `_LocalService` i, w ten sposób wyłączyć.

- Strona zabezpieczenia jest podobna do domyślnej strony zabezpieczeń znalezionej w oknie DCOMCNFG, z tą różnicą, że te ustawienia mają zastosowanie tylko do bieżącej aplikacji. Ponownie ustawienia są przechowywane w identyfikatorze AppID dla tego obiektu.

- Strona identyfikowanie identyfikuje użytkownika używanego do uruchamiania aplikacji.

- Na stronie punkty końcowe znajduje się zestaw protokołów i punktów końcowych dostępnych do użycia przez klientów wybranego serwera DCOM.

## <a name="see-also"></a>Zobacz też

[Usługi](../atl/atl-services.md)
