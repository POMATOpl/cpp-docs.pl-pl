---
title: Makra debugowania i raportowania błędów
ms.date: 05/06/2019
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
ms.openlocfilehash: 6b969cfb841a9a95d695eacc0a25f9dd378379ac
ms.sourcegitcommit: ced5ff1431ffbd25b20d106901955532723bd188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "92135544"
---
# <a name="debugging-and-error-reporting-macros"></a>Makra debugowania i raportowania błędów

Te makra zapewniają przydatne funkcje debugowania i śledzenia.

|Nazwa|Opis|
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|Zapisuje do okna danych wyjściowych wszystkie wycieki interfejsów, które są wykrywane, gdy `_Module.Term` jest wywoływana.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|Zapisuje wszystkie wywołania do `QueryInterface` okna danych wyjściowych.|
|[ATLASSERT](#atlassert)|Wykonuje te same funkcje jak makro [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Znalezione w bibliotece wykonawczej C.|
|[ATLENSURE](#atlensure)|Sprawdza poprawność parametrów. Wywołaj w `AtlThrow` razie konieczności|
|[ATLTRACENOTIMPL](#atltracenotimpl)|Wysyła komunikat do urządzenia zrzutu, którego określona funkcja nie jest zaimplementowana.|
|[ATLTRACE](#atltrace)|Raportuje ostrzeżenia do urządzenia wyjściowego, takie jak okno debugera, zgodnie ze wskazanymi flagami i poziomami. Uwzględnione w celu zapewnienia zgodności z poprzednimi wersjami.|
|[ATLTRACE2](#atltrace2)|Raportuje ostrzeżenia do urządzenia wyjściowego, takie jak okno debugera, zgodnie ze wskazanymi flagami i poziomami.|

## <a name="_atl_debug_interfaces"></a><a name="_atl_debug_interfaces"></a> _ATL_DEBUG_INTERFACES

Zdefiniuj to makro przed dołączeniem plików nagłówkowych ATL do śledzenia wszystkich `AddRef` i `Release` wywołań interfejsów składników do okna danych wyjściowych.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>Uwagi

Dane wyjściowe śledzenia będą wyświetlane jak pokazano poniżej:

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

Pierwsza część każdego śledzenia będzie zawsze `ATL: QIThunk` . Następnie jest wartością identyfikującą określony *interfejs thunk* . Interfejs thunk jest obiektem używanym do obsługi liczby odwołań i zapewniania funkcji śledzenia użytej w tym miejscu. Nowy interfejs thunk jest tworzony dla każdego wywołania z `QueryInterface` wyjątkiem żądań `IUnknown` interfejsu (w tym przypadku ten sam thunk jest zwracany za każdym razem, gdy są zgodne z regułami tożsamości modelu COM).

Następnie zobaczysz `AddRef` lub `Release` wskazują, która metoda została wywołana. Po wykonaniu tej czynności zobaczysz wartość identyfikującą obiekt, którego licznik odwołań interfejsu został zmieniony. Wartość śledzenia jest **`this`** wskaźnikiem obiektu.

Liczba odwołań, które są śledzone jest liczbą odwołań dla tego thunk po `AddRef` wywołaniu lub `Release` . Należy zauważyć, że ta liczba odwołań może nie odpowiadać liczbie odwołań dla obiektu. Każdy thunk utrzymuje własną liczbę odwołań, aby pomóc w całkowitym przestrzeganiu reguł zliczania odwołań COM.

Końcowa część informacji śledzenia jest nazwą obiektu i interfejsem, którego dotyczy `AddRef` lub `Release` wywołanie.

Wszelkie przecieki interfejsów wykrywane podczas zamykania serwera i `_Module.Term` wywoływane są następujące:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

Informacje podane w tym miejscu są mapowane bezpośrednio do informacji podanych w poprzednich instrukcjach śledzenia, dzięki czemu można przeanalizować liczby odwołań przez cały okres istnienia interfejsu thunk. Ponadto otrzymujesz wskazanie maksymalnej liczby odwołań dla tego interfejsu thunk.

> [!NOTE]
> _ATL_DEBUG_INTERFACES można używać w kompilacjach detalicznych.

## <a name="_atl_debug_qi"></a><a name="_atl_debug_qi"></a> _ATL_DEBUG_QI

Zapisuje wszystkie wywołania do `QueryInterface` okna danych wyjściowych.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>Uwagi

Jeśli wywołanie `QueryInterface` zakończyło się niepowodzeniem, zostanie wyświetlone okno dane wyjściowe:

*nazwa interfejsu* - `failed`

## <a name="atlassert"></a><a name="atlassert"></a> ATLASSERT

Makro ATLASSERT wykonuje te same funkcje jak makro [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) Znalezione w bibliotece wykonawczej C.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>Parametry

*booleanExpression*<br/>
Wyrażenie (w tym wskaźniki), które ma wartość różną od zera lub 0.

### <a name="remarks"></a>Uwagi

W kompilacjach debugowania ATLASSERT oblicza *booleanExpression* i generuje raport debugowania, gdy wynik ma wartość false.

### <a name="requirements"></a>Wymagania

**Nagłówek:** atldef. h

## <a name="atlensure"></a><a name="atlensure"></a> ATLENSURE

To makro służy do sprawdzania poprawności parametrów przesyłanych do funkcji.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>Parametry

*booleanExpression*<br/>
Określa wyrażenie logiczne, które ma zostać przetestowane.

*godz.*<br/>
Określa kod błędu, który ma zostać zwrócony.

### <a name="remarks"></a>Uwagi

Te makra zapewniają mechanizm wykrywania i powiadamiania użytkownika o nieprawidłowym użyciu parametrów.

Makro wywołuje ATLASSERT i jeśli warunek kończy się niepowodzeniem wywołań `AtlThrow` .

W przypadku ATLENSURE `AtlThrow` jest wywoływana z E_FAIL.

W ATLENSURE_THROW przypadku `AtlThrow` jest wywoływana z określonym wartością HRESULT.

Różnica między ATLENSURE i ATLASSERT polega na tym, że ATLENSURE zgłasza wyjątek w kompilacjach wydania, a także w kompilacjach debugowania.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

### <a name="requirements"></a>Wymagania

**Nagłówek:** AFX. h

## <a name="atltracenotimpl"></a><a name="atltracenotimpl"></a> ATLTRACENOTIMPL

W przypadku kompilacji debugowania ATL program wysyła ciąg " *FuncName* nie jest zaimplementowany" do urządzenia zrzutu i zwraca E_NOTIMPL.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>Parametry

*FuncName*<br/>
podczas Ciąg zawierający nazwę funkcji, która nie jest zaimplementowana.

### <a name="remarks"></a>Uwagi

W kompilacjach wydań po prostu zwraca E_NOTIMPL.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

### <a name="requirements"></a>Wymagania

**Nagłówek:** ATLTRACE. h

## <a name="atltrace"></a><a name="atltrace"></a> ATLTRACE

Raportuje ostrzeżenia do urządzenia wyjściowego, takie jak okno debugera, zgodnie ze wskazanymi flagami i poziomami. Uwzględnione w celu zapewnienia zgodności z poprzednimi wersjami.

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>Parametry

*EXP*<br/>
podczas Ciąg i zmienne do wysłania do okna danych wyjściowych lub dowolnej aplikacji, która Zalewka tych komunikatów.

*kategorii*<br/>
podczas Typ zdarzenia lub metody, które mają zostać objęte raportem. Zapoznaj się z uwagami dotyczącymi listy kategorii.

*poziom*<br/>
podczas Poziom śledzenia do raportu. Zobacz uwagi, aby uzyskać szczegółowe informacje.

*lpszFormat*<br/>
podczas Sformatowany ciąg, który ma zostać wysłany do urządzenia zrzutu.

### <a name="remarks"></a>Uwagi

Zobacz [ATLTRACE2](#atltrace2) , aby uzyskać opis ATLTRACE. ATLTRACE i ATLTRACE2 mają takie samo zachowanie, ATLTRACE jest uwzględniana w celu zapewnienia zgodności z poprzednimi wersjami.

## <a name="atltrace2"></a><a name="atltrace2"></a> ATLTRACE2

Raportuje ostrzeżenia do urządzenia wyjściowego, takie jak okno debugera, zgodnie ze wskazanymi flagami i poziomami.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTR lpszFormat,  ...);
```

### <a name="parameters"></a>Parametry

*EXP*<br/>
podczas Ciąg do wysłania do okna danych wyjściowych lub dowolnej aplikacji, która Zalewka tych komunikatów.

*kategorii*<br/>
podczas Typ zdarzenia lub metody, które mają zostać objęte raportem. Zapoznaj się z uwagami dotyczącymi listy kategorii.

*poziom*<br/>
podczas Poziom śledzenia do raportu. Zobacz uwagi, aby uzyskać szczegółowe informacje.

*lpszFormat*<br/>
podczas `printf`Ciąg formatujący styl, który ma zostać użyty do utworzenia ciągu do wysłania do urządzenia zrzutu.

### <a name="remarks"></a>Uwagi

Krótka forma ATLTRACE2 zapisuje ciąg w oknie danych wyjściowych debugera. Druga forma ATLTRACE2 również zapisuje dane wyjściowe w oknie danych wyjściowych debugera, ale podlega ustawieniom narzędzia śledzenia ATL/MFC (zobacz [przykład ATLTraceTool](../../overview/visual-cpp-samples.md)). Na przykład jeśli ustawisz *poziom* na 4 i Narzędzie śledzenia ATL/MFC do poziomu 0, komunikat nie zostanie wyświetlony. *poziom* może mieć wartość 0, 1, 2, 3 lub 4. Wartość domyślna to 0, co zgłasza jedynie poważne problemy.

Parametr *Category* zawiera listę flag śledzenia do ustawienia. Flagi te odpowiadają typom metod, dla których chcesz utworzyć raport. W poniższych tabelach znajduje się lista prawidłowych flag śledzenia, których można użyć dla parametru *kategorii* .

### <a name="atl-trace-flags"></a>Flagi śledzenia ATL

|Kategoria ATL|Opis|
|------------------|-----------------|
|`atlTraceGeneral`|Raporty dotyczące wszystkich aplikacji ATL. Domyślnie.|
|`atlTraceCOM`|Raporty dotyczące metod COM.|
|`atlTraceQI`|Raporty dotyczące wywołań QueryInterface.|
|`atlTraceRegistrar`|Raporty dotyczące rejestracji obiektów.|
|`atlTraceRefcount`|Raporty dotyczące zmiany liczby odwołań.|
|`atlTraceWindowing`|Raporty dotyczące metod systemu Windows; na przykład program zgłosi nieprawidłowy identyfikator mapy komunikatów.|
|`atlTraceControls`|Raporty dotyczące kontrolek; na przykład raportuje, gdy kontrolka lub jego okno są niszczone.|
|`atlTraceHosting`|Raporty hostingu komunikatów; na przykład raport jest uaktywniany po aktywowaniu klienta w kontenerze.|
|`atlTraceDBClient`|Raporty dotyczące szablonu OLE DB konsumenta; na przykład, gdy wywołanie elementu GetData nie powiedzie się, dane wyjściowe mogą zawierać wynik HRESULT.|
|`atlTraceDBProvider`|Raporty dotyczące szablonu dostawcy OLE DB; na przykład raporty, jeśli utworzenie kolumny nie powiodło się.|
|`atlTraceSnapin`|Raporty dla aplikacji przystawki programu MMC.|
|`atlTraceNotImpl`|Zgłasza, że wskazana funkcja nie jest zaimplementowana.|
|`atlTraceAllocation`|Raporty komunikatów wydrukowanych przez narzędzia debugowania pamięci w atldbgmem. h.|

### <a name="mfc-trace-flags"></a>Flagi śledzenia MFC

|Kategoria MFC|Opis|
|------------------|-----------------|
|`traceAppMsg`|Ogólnego przeznaczenia, komunikaty MFC. Zawsze zalecane.|
|`traceDumpContext`|Komunikaty z [CDumpContext](../../mfc/reference/cdumpcontext-class.md).|
|`traceWinMsg`|Komunikaty z kodu obsługującego komunikat MFC.|
|`traceMemory`|Komunikaty z kodu zarządzania pamięcią MFC.|
|`traceCmdRouting`|Komunikaty z kodu routingu poleceń systemu Windows MFC.|
|`traceHtml`|Komunikaty z obsługi okna dialogowego DHTML.|
|`traceSocket`|Komunikaty z obsługi gniazda MFC.|
|`traceOle`|Komunikaty z obsługi OLE MFC.|
|`traceDatabase`|Komunikaty z obsługi bazy danych MFC.|
|`traceInternet`|Komunikaty z obsługi Internetu MFC.|

Aby zadeklarować niestandardową kategorię śledzenia, zadeklaruj globalne wystąpienie `CTraceCategory` klasy w następujący sposób:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

Nazwa kategorii, MY_CATEGORY w tym przykładzie, to nazwa określona dla parametru *kategorii* . Pierwszy parametr jest nazwą kategorii, która będzie wyświetlana w narzędziu śledzenia ATL/MFC. Drugi parametr jest domyślnym poziomem śledzenia. Ten parametr jest opcjonalny, a domyślny poziom śledzenia to 0.

Aby użyć kategorii zdefiniowanej przez użytkownika:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

Aby określić, że chcesz filtrować komunikaty śledzenia, Wstaw definicje tych makr do stdafx. h przed `#include <atlbase.h>` instrukcją.

Alternatywnie można ustawić filtr w dyrektywach preprocesora w oknie dialogowym **strony właściwości** . Kliknij kartę **preprocesora** , a następnie Wstaw globalne do pola edycji **Definicje preprocesora** .

Atlbase. h zawiera definicje domyślne makr ATLTRACE2 i definicje te będą używane, jeśli nie zostaną zdefiniowane te symbole przed przetworzeniem atlbase. h.

W kompilacjach wydania ATLTRACE2 kompiluje do `(void) 0` .

ATLTRACE2 ogranicza zawartość ciągu, który ma być wysyłany na urządzenie zrzutu do nie więcej niż 1023 znaków po formatowaniu.

ATLTRACE i ATLTRACE2 mają takie samo zachowanie, ATLTRACE jest uwzględniana w celu zapewnienia zgodności z poprzednimi wersjami.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>Zobacz także

[Makra](../../atl/reference/atl-macros.md)<br/>
[Funkcje globalne debugowania i raportowania błędów](../../atl/reference/debugging-and-error-reporting-global-functions.md)
