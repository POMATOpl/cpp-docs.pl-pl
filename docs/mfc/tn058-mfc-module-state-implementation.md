---
description: 'Dowiedz się więcej o: TN058: implementacja stanu modułu MFC'
title: 'TN058: implementacja stanu modułu MFC'
ms.date: 06/28/2018
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
ms.openlocfilehash: c4b300b9aa184e9fa1c6cfd5a8cf668d163d85ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214783"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: implementacja stanu modułu MFC

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Ta Uwaga techniczna zawiera opis implementacji konstrukcji "stan modułu" MFC. Zrozumienie implementacji stanu modułu ma kluczowe znaczenie dla użycia udostępnionych bibliotek DLL MFC z biblioteki DLL (lub serwera w procesie OLE).

Przed zapisaniem tej uwagi zapoznaj się z tematem "Zarządzanie danymi stanu modułów MFC" w temacie [Tworzenie nowych dokumentów, okien i widoków](../mfc/creating-new-documents-windows-and-views.md). Ten artykuł zawiera ważne informacje dotyczące użycia i omówienia tego tematu.

## <a name="overview"></a>Omówienie

Istnieją trzy rodzaje informacji o stanie MFC: stan modułu, stan procesu i stan wątku. Czasami te typy stanów mogą być połączone. Na przykład mapy obsługi MFC są zarówno lokalne, jak i lokalne wątku. Dzięki temu dwa różne moduły mogą mieć różne mapy w poszczególnych wątkach.

Stan procesu i stan wątku są podobne. Te elementy danych są elementami, które tradycyjnie są zmiennymi globalnymi, ale muszą być specyficzne dla danego procesu lub wątku w celu zapewnienia odpowiednich obsługi systemu Win32 lub w celu zapewnienia odpowiedniej obsługi wielowątkowości. Kategoria, w której znajduje się dany element danych, zależy od tego elementu i jego pożądanej semantyki w odniesieniu do granic procesu i wątku.

Stan modułu jest unikatowy w tym, że może on zawierać prawdziwie globalny stan lub stan, który jest procesem lokalnym lub wątkiem lokalnym. Ponadto można je szybko przełączać.

## <a name="module-state-switching"></a>Przełączanie stanu modułu

Każdy wątek zawiera wskaźnik do stanu modułu "Current" lub "Active" (nie Surprisingly, wskaźnik jest częścią stanu lokalnego wątku MFC). Ten wskaźnik jest zmieniany, gdy wątek wykonywania przekazuje granicę modułu, taką jak aplikacja wywołująca formant OLE lub DLL, lub kontrolka OLE wywołująca z powrotem do aplikacji.

Bieżący stan modułu jest przełączany przez wywołanie `AfxSetModuleState` . W większości przypadków nigdy nie będziesz ponosić bezpośrednio z interfejsem API. MFC, w wielu przypadkach, wywoła je dla Ciebie (w WinMain, punkty wejścia OLE, `AfxWndProc` itp.). Jest to wykonywane w dowolnym składniku, który można napisać, statycznie łącząc w specjalny `WndProc` i specjalny `WinMain` (lub `DllMain` ), który wie, który stan modułu powinien być bieżący. Możesz zobaczyć ten kod, patrząc na DLLMODUL. CPP lub APPMODUL. CPP w katalogu MFC\SRC.

Jest to rzadki przypadek, w którym chcesz ustawić stan modułu, a następnie nie należy go ponownie ustawić. Większość czasu, w którym chcesz "wypchnąć" swój stan modułu jako bieżący, a następnie po zakończeniu "pop" oryginalny kontekst z powrotem. Jest to realizowane przez [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) makro i specjalną klasę `AFX_MAINTAIN_STATE` .

`CCmdTarget` ma specjalne funkcje do obsługi przełączania stanu modułu. W szczególności `CCmdTarget` jest klasą główną służącą do automatyzacji OLE i punktów wejścia OLE com. Podobnie jak w przypadku każdego innego punktu wejścia uwidocznionego w systemie, te punkty wejścia muszą określać prawidłowy stan modułu. Jak to wiadomo, `CCmdTarget` co oznacza, że stan modułu "prawidłowy" powinien być odpowiedzią, że jest to "Remember", co jest stanem modułu "bieżący", w taki sposób, że może ustawić bieżący stan modułu na tę wartość "zapamiętane" po jego późniejszej wywołaniu. W związku z tym stan modułu, z którym skojarzony jest dany `CCmdTarget` obiekt, to stan modułu, który był bieżący podczas konstruowania obiektu. Zapoznaj się z prostym przykładem ładowania serwera InProc, tworzenia obiektu i wywoływania jego metod.

1. Biblioteka DLL jest ładowana przez OLE przy użyciu polecenia `LoadLibrary` .

1. `RawDllMain` jest wywoływana jako pierwsza. Ustawia stan modułu na znany stan modułu statycznego dla biblioteki DLL. Z tego powodu `RawDllMain` statycznie połączone z biblioteką DLL.

1. Konstruktor klasy fabryki klas skojarzonej z naszym obiektem jest wywoływany. `COleObjectFactory` jest wyprowadzany z `CCmdTarget` i w wyniku, zapamiętuje, w którym stanie modułu został utworzony. Jest to ważne — gdy fabryka klas jest proszony o tworzenie obiektów, wie teraz, jaki stan modułu ma być obecny.

1. `DllGetClassObject` jest wywoływana w celu uzyskania fabryki klas. MFC przeszukuje listę fabryki klas skojarzoną z tym modułem i zwraca ją.

1. `COleObjectFactory::XClassFactory2::CreateInstance` jest wywoływana. Przed utworzeniem obiektu i zwróceniem go, ta funkcja ustawia stan modułu na stan modułu, który był bieżący w kroku 3 (ten, który był bieżący podczas `COleObjectFactory` tworzenia wystąpienia). Odbywa się to w [METHOD_PROLOGUE](com-interface-entry-points.md).

1. Gdy obiekt zostanie utworzony, jest on zbyt `CCmdTarget` pochodny i w ten sam sposób `COleObjectFactory` pamiętam, który stan modułu był aktywny, więc robi ten nowy obiekt. Teraz obiekt wie, który stan modułu należy przełączyć, gdy jest on wywoływany.

1. Klient wywołuje funkcję w obiekcie OLE COM otrzymany od jego `CoCreateInstance` wywołania. Gdy obiekt jest wywoływany przez niego używa `METHOD_PROLOGUE` do przełączania stanu modułu tak samo jak w przypadku `COleObjectFactory` .

Jak widać, stan modułu jest propagowany z obiektu do obiektu w miarę ich tworzenia. Ważne jest, aby ustawić stan modułu odpowiednio. Jeśli nie jest ustawiona, obiekt DLL lub COM może działać niewłaściwie z aplikacją MFC, która wywołuje ten element, lub może nie być w stanie znaleźć własnych zasobów lub może się nie powieść w innych Marne sposobów.

Należy pamiętać, że niektóre rodzaje bibliotek DLL, w tym biblioteki DLL rozszerzenia MFC, nie przełączają stanu modułu w ich `RawDllMain` (w rzeczywistości zazwyczaj nie mają `RawDllMain` ). Dzieje się tak, ponieważ są one przeznaczone do zachowania "tak jakby" były rzeczywiście obecne w aplikacji, która z nich korzysta. Są one bardzo duże częścią aplikacji, która jest uruchomiona i zamiarem zmiany stanu globalnego aplikacji.

Formanty OLE i inne biblioteki DLL są bardzo różne. Nie chcą modyfikować stanu aplikacji wywołującej; aplikacja, która wywołuje je, może nie być nawet aplikacją MFC i dlatego nie może być modyfikowana. Przyczyną jest to, że nastąpiło przełączenie stanu modułu.

W przypadku eksportowanych funkcji z biblioteki DLL, takich jak ten, który uruchamia okno dialogowe w bibliotece DLL, należy dodać następujący kod na początku funkcji:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

Spowoduje to zamianę bieżącego stanu modułu na stan zwrócony z [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) do końca bieżącego zakresu.

Problemy z zasobami w bibliotekach DLL pojawią się, jeśli makro AFX_MODULE_STATE nie jest używane. Domyślnie MFC używa dojścia do zasobów głównej aplikacji do ładowania szablonu zasobu. Ten szablon jest w rzeczywistości przechowywany w bibliotece DLL. Główną przyczyną jest to, że informacje o stanie modułu MFC nie zostały przełączone przez makro AFX_MODULE_STATE. Dojście do zasobu jest odzyskiwane z stanu modułu MFC. Nie przełączenie stanu modułu powoduje niewłaściwe użycie uchwytu zasobów.

AFX_MODULE_STATE nie musi być umieszczony w każdej funkcji w bibliotece DLL. Na przykład `InitInstance` może być wywoływana przez kod MFC w aplikacji bez AFX_MODULE_STATE, ponieważ MFC automatycznie przesuwa stan modułu przed `InitInstance` , a następnie przełącza je ponownie po `InitInstance` powrocie. Ta sama wartość dotyczy wszystkich programów obsługi mapy komunikatów. Regularne biblioteki MFC DLL faktycznie mają specjalną procedurę okna głównego, która automatycznie przełącza stan modułu przed kierowaniem jakichkolwiek komunikatów.

## <a name="process-local-data"></a>Przetwarzanie danych lokalnych

Dane lokalne procesu nie będą miały tego doskonałego znaczenia, gdyby nie dotyczyły one problemu z modelem DLL Win32s. W systemie Win32 wszystkie biblioteki DLL współdzielą swoje dane globalne nawet w przypadku ładowania ich przez wiele aplikacji. Jest to bardzo różne od "rzeczywistego" modelu danych Win32 DLL, gdzie każda biblioteka DLL pobiera oddzielną kopię przestrzeni danych w każdym procesie dołączanym do biblioteki DLL. Aby dodać do złożoności, dane przydzielono na stercie w bibliotece DLL Win32s są w rzeczywistości specyficzne dla procesu (co najmniej tak długo, jak ma miejsce własność). Należy wziąć pod uwagę następujące dane i kod:

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

Zastanów się, co się stanie, Jeśli powyższy kod znajduje się w bibliotece DLL i ten plik DLL jest ładowany przez dwa procesy A i B (może to być w rzeczywistości dwa wystąpienia tej samej aplikacji). Wywołania `SetGlobalString("Hello from A")` . W związku z tym pamięć jest przypisana do `CString` danych w kontekście procesu a. należy pamiętać, że `CString` sama jest globalna i widoczna zarówno dla a, jak i B. Teraz B wywołania `GetGlobalString(sz, sizeof(sz))` . B będzie można zobaczyć dane, które są ustawione. Wynika to z faktu, że Win32s nie oferuje żadnej ochrony między procesami, takimi jak Win32. Jest to pierwszy problem; w wielu przypadkach nie jest wymagane, aby jedna aplikacja miała wpływ na dane globalne, które są traktowane jako należące do innej aplikacji.

Istnieją również dodatkowe problemy. Załóżmy, że teraz kończy się. Po zakończeniu, pamięć użyta przez `strGlobal` ciąg "" jest udostępniana dla systemu — to znaczy, że cała pamięć przyalokowana przez proces A jest zwalniana automatycznie przez system operacyjny. Nie jest on zwolniony, ponieważ `CString` destruktor jest wywoływany; nie został jeszcze wywołany. Jest ona zwalniana po prostu, ponieważ aplikacja, która ją przydzieliła, opuściła scenę. Teraz w przypadku wywołania B `GetGlobalString(sz, sizeof(sz))` może nie być możliwe uzyskanie prawidłowych danych. Niektóre inne aplikacje mogły korzystać z tej pamięci w inny sposób.

Jasno występuje problem. MFC 3. x używa techniki nazywanej magazynem wątków-Local (TLS). MFC 3. x przydzieli indeks TLS, który w obszarze Win32s naprawdę działa jako indeks magazynu lokalnego procesu, nawet jeśli nie jest on wywoływany, a następnie będzie odwoływać się do wszystkich danych opartych na tym indeksie protokołu TLS. Jest to podobne do indeksu protokołu TLS, który został użyty do przechowywania danych lokalnych wątku w systemie Win32 (zobacz poniżej, aby uzyskać więcej informacji na temat tego tematu). Spowodowało to użycie co najmniej dwóch indeksów TLS dla procesu. W przypadku załadowania wielu bibliotek DLL formantów OLE (OCXs) można szybko wylogować się z indeksów protokołu TLS (dostępne są tylko 64). Ponadto MFC musiało umieścić wszystkie te dane w jednym miejscu, w jednej strukturze. Nie było to bardzo rozszerzalne i nie było idealne w odniesieniu do użycia indeksów TLS.

MFC 4. x rozwiązuje ten zestaw szablonów klas można "otoczyć" danymi, które powinny być przetwarzane lokalnie. Na przykład problem opisany powyżej może zostać rozwiązany przez zapisanie:

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC implementuje to w dwóch krokach. Najpierw istnieje warstwa na podstawie interfejsów API __protokołu Win32 \* TLS__ (**Funkcja TlsAlloc**, **TlsSetValue**, **TlsGetValue** itp.), które używają tylko dwóch indeksów protokołu TLS dla każdego procesu, niezależnie od liczby posiadanych bibliotek DLL. Po drugie, `CProcessLocal` szablon jest dostarczany, aby uzyskać dostęp do tych danych. Zastępuje on > operatora, co umożliwia intuicyjną składnię wyświetlaną powyżej. Wszystkie obiekty, które są opakowane przez, `CProcessLocal` muszą pochodzić od `CNoTrackObject` . `CNoTrackObject`zapewnia Alokator niższego poziomu (**LocalAlloc** / **LocalFree**) i destruktor wirtualny, aby MFC mógł automatycznie zniszczyć obiekty lokalne procesu po zakończeniu procesu. Takie obiekty mogą mieć niestandardowy destruktor, jeśli wymagane jest dodatkowe oczyszczanie. Powyższy przykład nie wymaga takiego, ponieważ kompilator generuje domyślny destruktor, aby zniszczyć osadzony `CString` obiekt.

Takie podejście ma inne interesujące zalety. Wszystkie `CProcessLocal` obiekty są niszczone automatycznie, ale nie są konstruowane do momentu ich zamiaru. `CProcessLocal::operator->` spowoduje utworzenie wystąpienia skojarzonego obiektu przy pierwszym wywołaniu i brak wcześniej. W powyższym przykładzie oznacza to, że `strGlobal` ciąg "" nie zostanie skonstruowany do czasu pierwszej `SetGlobalString` lub `GetGlobalString` wywołania. W niektórych przypadkach może to pomóc w zmniejszeniu czasu uruchamiania biblioteki DLL.

## <a name="thread-local-data"></a>Dane lokalne wątku

Podobnie jak w przypadku przetwarzania danych lokalnych, dane lokalne wątku są używane, gdy dane muszą być lokalne dla danego wątku. Oznacza to, że potrzebne jest oddzielne wystąpienie danych dla każdego wątku, który uzyskuje dostęp do tych danych. Może to być wiele razy używane zamiast szerokiego mechanizmu synchronizacji. Jeśli dane nie muszą być współużytkowane przez wiele wątków, takie mechanizmy mogą być kosztowne i niepotrzebne. Załóżmy, że mamy `CString` obiekt (podobnie jak powyżej przykładu). Możemy uczynić wątek IT lokalnym, zawijając go przy użyciu `CThreadLocal` szablonu:

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

Jeśli `MakeRandomString` został wywołany z dwóch różnych wątków, każdy z nich będzie "losowo" w różny sposób, bez zakłócania drugiego. Wynika to z faktu, że w rzeczywistości istnieje `strThread` wystąpienie na wątek zamiast tylko jednego wystąpienia globalnego.

Zwróć uwagę na to, jak odwołanie jest używane do przechwycenia `CString` adresu raz, a nie raz na iterację pętli. Kod pętli mógł zostać zapisany `threadData->strThread` wszędzie tam `str` , gdzie jest używany element "", ale kod może być dużo wolniejszy w wykonywaniu. Najlepszym rozwiązaniem jest buforowanie odniesienia do danych, gdy takie odwołania występują w pętlach.

`CThreadLocal`Szablon klasy używa tych samych mechanizmów, które są takie same `CProcessLocal` jak te same metody implementacji.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
