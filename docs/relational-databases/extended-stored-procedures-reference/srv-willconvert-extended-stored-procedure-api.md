---
title: srv_willconvert (拡張ストアド プロシージャ API) | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
apiname:
- srv_willconvert
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: ec59e76cb90612a2a1dd8fd54f2ee71967a09606
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2019
ms.locfileid: "68036018"
---
# <a name="srvwillconvert-extended-stored-procedure-api"></a>srv_willconvert (拡張ストアド プロシージャ API)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]代わりに CLR Integration をご使用ください。  
  
 ODS Library 内で特定のデータ型の変換が可能かどうかを判定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
```  
  
## <a name="arguments"></a>引数  
 *srctype*  
 変換するソース データのデータ型を示します。 このパラメーターには、拡張ストアド プロシージャ API の任意のデータ型を使用できます。  
  
 *desttype*  
 ソース データを変換した後のデータ型を示します。 このパラメーターには、拡張ストアド プロシージャ API の任意のデータ型を使用できます。  
  
## <a name="returns"></a>戻り値  
 データ型の変換がサポートされている場合は TRUE を返します。サポートされていない場合は FALSE を返します。  
  
## <a name="remarks"></a>Remarks  
 各データ型については、「[データ型 &#40;拡張ストアド プロシージャ API&#41;](../../relational-databases/extended-stored-procedures-reference/data-types-extended-stored-procedure-api.md)」をご覧ください。  
  
> [!IMPORTANT]  
>  拡張ストアド プロシージャのソース コードを十分に確認し、コンパイル済み DLL を、運用サーバーにインストールする前にテストする必要があります。 セキュリティの確認およびテストについて詳しくは、[Microsoft の Web サイト](https://www.microsoft.com/en-us/msrc?rtc=1)をご覧ください。  
  
## <a name="see-also"></a>参照  
 [srv_convert &#40;拡張ストアド プロシージャ API&#41;](../../relational-databases/extended-stored-procedures-reference/srv-convert-extended-stored-procedure-api.md)  
  
  
