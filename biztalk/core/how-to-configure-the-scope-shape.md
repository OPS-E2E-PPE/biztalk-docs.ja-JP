---
title: スコープ図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], about Scope shape
- Scope shape [Orchestration Designer], configuring
- Scope shape [Orchestration Designer], variables
- Scope shape [Orchestration Designer]
- configuring [Orchestration Designer], Scope shape
- Scope shape [Orchestration Designer], transactions
ms.assetid: 3c518db0-d68c-4f72-9d5c-48540811e289
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5627f3463b1d2797abe742462cf60e948e8bbb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340415"
---
# <a name="how-to-configure-the-scope-shape"></a>スコープ図形を構成する方法
**スコープ**図形は、その内容に状況に応じたフレームワークを提供します。 最初のブロックを**スコープ**図形はコンテキスト ブロック、つまりボディ、これで、スコープの基本的な操作が行わ; try/catch ステートメントの try ブロックと似ています。 、ボディ部に続いて、**スコープ**図形が 1 つまたは複数の例外ハンドラー ブロックや補正ブロックに含めることもできます。  
  
> [!NOTE]
>  複数マシン環境で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]世界協定時刻 (UTC) が 2 台のコンピューターと異なる場合、SQL Server が別のコンピューターに存在し、**タイムアウト**プロパティ、用に構成します。**スコープ**図形で UTC 時間であるために予想よりも早くトリガーが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と SQL Server マシンは同期されていません。 ないタイム ゾーンの問題を世界協定時刻が影響を受けることは、タイム ゾーンではないために注意してください。  
  
### <a name="to-configure-a-scope-shape-as-a-transaction-boundary"></a>スコープ図形をトランザクション境界として構成するには  
  
1.  [プロパティ] ウィンドウで次のように設定します。、**トランザクションの種類**プロパティを**アトミック**または**長時間**します。  
  
    > [!NOTE]
    >  オーケストレーション自体もをアトミックまたは長時間トランザクションの種類を設定するために、実行時間の長いトランザクション。  
  
2.  場合、**トランザクションの種類**に設定されている**アトミック**、し、[プロパティ] ウィンドウで、次のプロパティを指定します。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |Batch (バッチ)|このトランザクションをオーケストレーションの複数のインスタンスの他のトランザクションとバッチことができるかどうかを決定するブール値。 BizTalk Server は、アトミック トランザクションをバッチ処理オーケストレーションの複数のインスタンスをサポートしていないために、このプロパティは BizTalk Server で使用されません。 このプロパティは、将来のリリースで非推奨とされます。|  
    |[分離レベル]|データの同時実行トランザクション間でアクセスできる程度を決定します。<br /><br /> -Read Committed などを選択したトランザクションがコミットされるまでの同時実行トランザクションで変更されたデータへのアクセスを防ぐためにします。 このオプションは、Microsoft SQL Server の既定の設定です。<br />不能反復読み取り、選択したトランザクションが完了するまで、読み取りロックを要求するようにします。<br />シリアル化できる、同時実行トランザクションから、選択したトランザクションが完了するまでデータを変更します。 このオプションは、最も制限の厳しい分離レベルです。|  
    |[再試行]|エラーが発生したときに、このトランザクションを再試行するかどうかを決定するブール値。 既定値は **True**です。 **注:** Microsoft.XLANG.BaseTypes.RetryTransactionException をスローする場合、またはオーケストレーション エンジンがその状態を保管するため、トランザクションをコミットできない場合は、アトミックのトランザクションが再試行されます。|  
    |Timeout|非アクティブなトランザクションが失敗するまでの秒単位の時間を決定します。 タイムアウトを使用しない場合は、このプロパティの値を 0 に設定します。 **注:** これは、DTC タイムアウトであり、オーケストレーション エンジンによっては適用されません。 アトミック トランザクションのみの場合、エンジンは、トランザクションを中断しません。 通常、内のオブジェクトのいずれかで DTC トランザクションに参加している場合にのみコミットに失敗した時点で、コミットされるまで進行します。|  
  
3.  場合、**トランザクションの種類**に設定されている**長時間**、[プロパティ] ウィンドウで、次のプロパティを指定します。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |Timeout|トランザクションがタイムアウトになると、失敗したトランザクションと見なされますまでの秒単位の時間を決定します。 タイムアウトを使用しない場合は、このプロパティの値を 0 に設定します。|  
  
### <a name="to-configure-a-scope-shape-to-contain-local-variables"></a>ローカル変数を格納するスコープ図形を構成するには  
  
1.  オーケストレーションの種類 ウィンドウでスコープをダブルクリックします。  
  
2.  [スコープ]、[変数] フォルダーを右クリックし、をクリックし、**新しい変数**します。  
  
3.  手順 2.「変数を追加するには」に進める[オーケストレーション変数の追加方法](../core/how-to-add-orchestration-variables.md)します。