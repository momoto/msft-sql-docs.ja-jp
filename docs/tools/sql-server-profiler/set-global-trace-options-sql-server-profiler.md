---
title: グローバルトレースオプションの設定 (SQL Server プロファイラー) |Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- global trace options [SQL Server]
ms.assetid: 2854608a-c3c7-4eb8-b567-034bfec4b1a9
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 9605f5e12b1dcc206d50e958d8c1787750e98941
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2019
ms.locfileid: "68104179"
---
# <a name="set-global-trace-options-sql-server-profiler"></a>グローバル トレース オプションの設定 (SQL Server Profiler)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  このトピックでは、 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]の特定のインスタンスで作成したすべてのトレースに適用するオプションの設定方法について説明します。  
  
### <a name="to-set-global-trace-options"></a>グローバル トレース オプションを設定するには  
  
1.  **[ツール]** メニューの **[オプション]** をクリックします。  
  
2.  **[全般オプション]** ダイアログ ボックスで、 **[フォントの選択]** をクリックして表示オプションを変更し、 **[OK]** をクリックします。  
  
3.  必要に応じて、 **[接続の確立直後にトレースを開始する]** を選択します。  
  
4.  必要に応じて、 **[プロバイダーのバージョンが変更されたときに、トレース定義を更新する]** を選択します。 このオプションの使用をお勧めします。既定では、このオプションはオンになっています。 このオプションを選択した場合、トレース定義はトレースを実行するサーバーの現在のバージョンに自動的に更新されます。  
  
5.  必要に応じて、サーバーでロールオーバー ファイルを管理する方法を指定します。  
  
    -   再生時にロールオーバー ファイルを自動的に読み込むには、 **[確認せずにすべてのロールオーバー ファイルを順に読み込む]** を選択します。  
  
    -   再生時にロールオーバー ファイルを制御するには、 **[ロールオーバー ファイルを読み込む前に確認する]** を選択します。  
  
    -   一度に 1 つのファイルのみを再生するには、 **[後続のロールオーバー ファイルを読み込まない]** を選択します。  
  
6.  必要に応じて、再生オプションを設定します。  
  
    -   **[再生スレッドの既定の数]** では、再生時に使用するプロセッサ スレッドの数を制御します。 スレッド数を多くすると、再生は早く完了しますが、再生時にサーバーのパフォーマンスが低下します。 推奨設定値は **4**です。 次の表は、使用可能な値の一覧です。  
  
        |[値]|[説明]|  
        |-----------|-----------------|  
        |**2**|最小値です。 2 つのスレッドを使用して再生します。|  
        |**4**|既定値です。|  
        |**255**|最大値です。 最大値を設定すると、他のプロセスのパフォーマンスが低下します。|  
  
    -   **[ヘルス モニターの既定の待機間隔 (秒)]** では、再生スレッドが他のプロセスをブロックできる最長時間を秒単位で設定します。 次の表は、その値を示しています。  
  
        |[値]|[説明]|  
        |-----------|-----------------|  
        |**0**|最小値です。 **0** に設定すると、 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] によってブロック プロセスが停止されません。|  
        |**3600**|既定値です。 **3600** 秒 (1 時間) を超えないブロック プロセスを使用できます。|  
        |**86400**|最大値です。 **86400** 秒 (1 日) を超えないブロック プロセスを使用できます。|  
  
    -   **[ヘルス モニターの既定のポーリング間隔 (秒)]** では、ブロック プロセスの再生スレッドを呼び出す頻度を設定します。 次の表は、その値を示しています。  
  
        |[値]|[説明]|  
        |-----------|-----------------|  
        |**1**|最小値です。 **1** に設定すると、 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] によって毎秒 1 回ブロック プロセスが呼び出されます。|  
        |**60**|既定値です。 毎分 1 回ブロック プロセスを呼び出します。|  
        |**86400**|最大値です。 **86400** 秒 (1 日) に 1 回ブロック プロセスを呼び出します。|  
  
## <a name="see-also"></a>参照  
 [トレース表示の既定値の設定 &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
