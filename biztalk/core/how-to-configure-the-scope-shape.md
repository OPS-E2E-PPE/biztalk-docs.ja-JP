---
title: "スコープ図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], about Scope shape
- Scope shape [Orchestration Designer], configuring
- Scope shape [Orchestration Designer], variables
- Scope shape [Orchestration Designer]
- configuring [Orchestration Designer], Scope shape
- Scope shape [Orchestration Designer], transactions
ms.assetid: 3c518db0-d68c-4f72-9d5c-48540811e289
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef17f5d1ab94875af118d17551da4334525535fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-scope-shape"></a>スコープ図形を構成する方法
**スコープ**図形は、そのコンテンツの状況に応じたフレームワークを提供します。 最初のブロック、**スコープ**図形はコンテキスト ブロック、つまりボディ部をスコープの基本的なアクションが行わ以外の場合は、try/catch ステートメントの try ブロックと似ています。 次の本文、**スコープ**図形には、1 つまたは複数の例外ハンドラー ブロックや補正ブロックもを含めることがあります。  
  
> [!NOTE]
>  複数コンピューター環境で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]世界協定時刻 (UTC) が 2 つのコンピューターで異なる場合は、SQL Server を別のコンピューターに配置し、**タイムアウト**プロパティ、用に構成します。**スコープ**図形を UTC 時間であるために予想よりも前にトリガーを取得可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL Server マシンが同期されていないとします。 これはタイム ゾーンの問題ではありません。なぜなら、協定世界時はタイム ゾーンに影響されないからです。  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a>スコープ図形をトランザクション境界として構成するには  
  
1.  [プロパティ] ウィンドウで、設定、**トランザクションの種類**プロパティを**Atomic**または**長時間**です。  
  
    > [!NOTE]
    >  [トランザクションの種類] を [アトミック] または [長時間トランザクション] に設定するには、オーケストレーション自体が長時間トランザクションであることが必要です。  
  
2.  場合、**トランザクションの種類**に設定されている**Atomic**、[プロパティ] ウィンドウで、次のプロパティを指定します。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |Batch|このトランザクションと他のトランザクションをオーケストレーションの複数のインスタンスにまたがってバッチ処理できるかどうかを決定するブール値。 BizTalk Server では、オーケストレーションの複数のインスタンスにまたがるアトミック トランザクションのバッチ処理がサポートされません。したがって、BizTalk Server では、このプロパティは使用できません。 このプロパティは、将来のリリースで廃止される予定です。|  
    |[分離レベル]|同時実行トランザクション間でアクセスできるデータのレベルを指定します。<br /><br /> -Read Committed-選択したトランザクションがコミットされるまでの同時実行トランザクションで変更されたデータへのアクセスを防ぐためにします。 このオプションは Microsoft SQL Server の既定の設定です。<br />-Repeatable Read-選択したトランザクションが完了するまで、読み取りロックを要求するようにします。<br />化シリアルなど、同時実行トランザクションから選択したトランザクションが完了するまでデータを変更します。 このオプションは最も制限された分離レベルになります。|  
    |[再試行]|エラーが発生したときに、このトランザクションを再試行するかどうかを決定するブール値。 既定値は **True**です。 **注:** Microsoft.XLANG.BaseTypes.RetryTransactionException をスローする場合、またはオーケストレーション エンジンがその状態を保管するため、トランザクションをコミットできない場合、アトミック トランザクションは再試行されます。|  
    |Timeout|トランザクションが非アクティブな場合にエラーを発生させるまでの時間を秒単位で指定します。 タイムアウトを使用したくない場合は、このプロパティの値を 0 に設定します。 **注:**この DTC タイムアウトでは、オーケストレーション エンジンでは適用されません。 アトミック トランザクションの場合のみ、エンジンはトランザクションを中断しません。 エンジンは、DTC トランザクション内のいずれかのオブジェクトを介して DTC トランザクションに参加している場合のみ、コミットまで通常どおり処理し、コミット時にエラーを発生させます。|  
  
3.  場合、**トランザクションの種類**に設定されている**長時間**、[プロパティ] ウィンドウで、次のプロパティを指定します。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |Timeout|トランザクションがタイムアウトし、失敗したトランザクションと見なされるまでの時間を秒単位で指定します。 タイムアウトを使用したくない場合は、このプロパティの値を 0 に設定します。|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a>ローカル変数を格納するスコープ図形を構成するには  
  
1.  オーケストレーションの種類 ウィンドウでスコープをダブルクリックします。  
  
2.  [スコープ]、[変数] フォルダーを右クリックし、をクリックして**新しい変数**です。  
  
3.  「変数を追加するには」で、手順 2. を進める[オーケストレーション変数の追加方法](../core/how-to-add-orchestration-variables.md)です。