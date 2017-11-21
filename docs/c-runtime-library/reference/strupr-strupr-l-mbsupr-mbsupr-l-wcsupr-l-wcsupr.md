---
title: "_strupr —, _strupr_l —, _mbsupr —, _mbsupr_l —, _wcsupr_l —, _wcsupr — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsupr_l
- _mbsupr
- _strupr_l
- _wcsupr
- _wcsupr_l
- _strupr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbsupr
- _ftcsupr
- mbsupr
- _tcsupr
- strupr_l
- _fstrupr
- _strupr
- mbsupr_l
- _wcsupr
dev_langs: C++
helpviewer_keywords:
- tcsupr_l function
- mbsupr function
- strupr function
- uppercase, converting strings to
- wcsupr function
- _wcsupr function
- string conversion [C++], case
- ftcsupr function
- _ftcsupr function
- _wcsupr_l function
- wcsupr_l function
- strings [C++], case
- tcsupr function
- _tcsupr_l function
- _fstrupr function
- _strupr_l function
- _mbsupr_l function
- converting case, CRT functions
- fstrupr function
- mbsupr_l function
- strupr_l function
- _strupr function
- _mbsupr function
- _tcsupr function
- strings [C++], converting case
ms.assetid: caac8f16-c233-41b6-91ce-575ec7061b77
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 88362cf0100a7b8d118f38632e9751afa79ae4e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="strupr-struprl-mbsupr-mbsuprl-wcsuprl-wcsupr"></a>_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr
Konwertuje ciąg na wielkie litery. Bezpieczniejsza wersje te funkcje są dostępne; zobacz [_strupr_s —, _strupr_s_l —, _mbsupr_s —, _mbsupr_s_l —, _wcsupr_s —, _wcsupr_s_l —](../../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md).  
  
> [!IMPORTANT]
>  `_mbsupr`i `_mbsupr_l` nie można używać w aplikacjach, które są wykonywane w środowisku wykonawczym systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT, nie są obsługiwane z parametrem /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Składnia  
  
```  
char *_strupr(  
   char *str   
);  
wchar_t *_wcsupr(  
   wchar_t *str   
);  
unsigned char *_mbsupr(  
   unsigned char *str   
);  
char *_strupr_l(  
   char *str,  
   _locale_t locale  
);  
wchar_t *_wcsupr_l(  
   wchar_t *str,  
   _locale_t locale  
);  
unsigned char *_mbsupr_l(  
   unsigned char *str,  
   _locale_t locale  
);  
template <size_t size>  
char *_strupr(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wcsupr(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
unsigned char *_mbsupr(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
char *_strupr_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
wchar_t *_wcsupr_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
unsigned char *_mbsupr_l(  
   unsigned char (&str)[size],  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametry  
 `str`  
 Ciąg do wielką literą.  
  
 `locale`  
 Ustawienia regionalne do użycia.  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca wskaźnik do ciągu zmieniony. Ponieważ modyfikacja jest wykonywana w miejscu, wskaźnik zwracany jest taka sama jak wskaźnik przekazany jako argument wejściowy. Brak wartości zwracanej jest zarezerwowana wystąpił błąd.  
  
## <a name="remarks"></a>Uwagi  
 `_strupr` Funkcji konwertuje w miejscu, każdy małej litery w `str` na wielkie litery. Konwersja jest określany przez `LC_CTYPE` ustawienie kategorii ustawień regionalnych. Nie dotyczy innych znaków. Aby uzyskać więcej informacji na temat `LC_CTYPE`, zobacz [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Wersje tych funkcji bez `_l` sufiks Użyj bieżących ustawień regionalnych; wersji z `_l` sufiks są identyczne, z wyjątkiem tego, aby używały przekazano zamiast tego ustawienia regionalne. Aby uzyskać więcej informacji, zobacz [ustawień regionalnych](../../c-runtime-library/locale.md).  
  
 `_wcsupr`i `_mbsupr` znaków dwubajtowych i znaków wielobajtowych wersji `_strupr`. Wartość argumentów i `_wcsupr` są znaków dwubajtowych ciągi; tych `_mbsupr` są ciągami znaków wielobajtowych. Te trzy funkcje działają tak samo w przeciwnym razie wartość.  
  
 Jeśli `str` wskaźnika o wartości null, jest program obsługi nieprawidłowych parametrów zostanie wywołany, zgodnie z opisem w [sprawdzanie poprawności parametru](../../c-runtime-library/parameter-validation.md) . Jeśli jest dozwolone wykonywanie, aby kontynuować, te funkcje zwracane oryginalnego ciągu i zestaw `errno` do `EINVAL`.  
  
 W języku C++ te funkcje mają przeciążenia szablonu, które wywołują odpowiedników nowsza, bezpieczne tych funkcji. Aby uzyskać więcej informacji, zobacz [Secure szablonu Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu  
  
|Procedura TCHAR.H|_Unicode — & _MBCS nie zdefiniowany|_MBCS zdefiniowano|_UNICODE zdefiniowano|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsupr`|`_strupr`|`_mbsupr`|`_wcsupr`|  
|`_tcsupr_l`|`_strupr_l`|`_mbsupr_l`|`_wcsupr_l`|  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`_strupr`, `_strupr_l`|\<String.h >|  
|`_wcsupr`, `_wcsupr_l`|\<String.h > lub \<wchar.h >|  
|`_mbsupr`, `_mbsupr_l`|\<mbstring.h >|  
  
 Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Przykład  
 Zobacz przykład [_strlwr —](../../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Ustawienia regionalne](../../c-runtime-library/locale.md)   
 [Manipulowanie ciągami](../../c-runtime-library/string-manipulation-crt.md)   
 [_strlwr —, _wcslwr —, _mbslwr —, _strlwr_l — _wcslwr_l —, _mbslwr_l —](../../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)