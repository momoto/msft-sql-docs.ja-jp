---
title: ブレークポイント フィルターの指定 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint filter
ms.assetid: 7bf1dddd-7b0b-4c47-8a7b-28a5569b4fa5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c86f31bc79dae5c257f58d59bbfc8039e02f7e4e
ms.sourcegitcommit: 3026c22b7fba19059a769ea5f367c4f51efaf286
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2019
ms.locfileid: "66090119"
---
# <a name="specify-a-breakpoint-filter"></a>ブレークポイント フィルターの指定
  ブレークポイント フィルターは、ブレークポイントが指定したコンピューター、オペレーティング システム プロセス、およびスレッドだけで動作するように制限します。 通常、ブレークポイント フィルターは、並列アプリケーションをデバッグするときに使用されます。  
  
##  <a name="BKMK_ActionConsiderations"></a> フィルターに関する注意点  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] スクリプトおよびストアド プロシージャは並列アプリケーションではないため、ブレークポイント フィルターは [!INCLUDE[tsql](../../includes/tsql-md.md)] デバッガーでは通常使用されません。  
  
#### <a name="to-specify-a-breakpoint-filter"></a>ブレークポイント フィルターを指定するには  
  
1.  エディター ウィンドウで、ブレークポイント グリフを右クリックし、ショートカット メニューの **[フィルター]** をクリックします。  
  
     \- または -  
  
     **[ブレークポイント]** ウィンドウで、ブレークポイント グリフを右クリックし、ショートカット メニューの **[フィルター]** をクリックします。  
  
2.  **[ブレークポイント フィルター]** ダイアログ ボックスで、 **[フィルター]** ボックスを使用して、コンピューター名を指定するか、またはオペレーティング システム プロセスとスレッドを名前または ID 番号で指定します。  
  
    -   `MachineName` は、データベース エンジンのインスタンスを実行しているコンピューターです。  
  
    -   `ProcessID` および `ProcessName` は、データベース エンジンのインスタンスを実行しているオペレーティング システム プロセスです。  
  
    -   `ThreadID` および `ThreadName` は、データベース エンジンのインスタンス内で [!INCLUDE[tsql](../../includes/tsql-md.md)] バッチ、プロシージャ、または関数を実行しているオペレーティング システム スレッドです。  
  
3.  **[OK]** をクリックして変更を適用するか、 **[キャンセル]** をクリックして変更を適用せずに終了します。  
  
## <a name="see-also"></a>参照  
 [ブレークポイント条件の指定](specify-a-breakpoint-condition.md)   
 [ヒット カウントの指定](specify-a-hit-count.md)   
 [ブレークポイント アクションの指定](specify-a-breakpoint-action.md)  
