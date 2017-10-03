---
title: "メッセージを検索する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-messages"></a>メッセージを検索する方法
使用することができます、**クエリ** タブでメッセージの特定のクラスを検索するには、BizTalk Server 管理コンソールです。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-messages"></a>メッセージを検索するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3.  詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。  
  
4.  **クエリ式**グループにおいて、**値**列で、選択**メッセージ**ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |アイテム|Description|  
    |----------|-----------------|  
    |**作成日時**|指定した日時の前または後に作成されたメッセージを検索します。|  
    |**エラー アダプター**|グループ化できますまたはアダプターの種類別にメッセージをフィルター処理: ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、または Windows SharePoint Services です。|  
    |**エラー コード**|メッセージをエラー コードでグループ化またはフィルター選択できます。|  
    |**エラーの説明**|メッセージをエラーの説明でグループ化またはフィルター選択できます。|  
    |**Host Name**|メッセージをホスト名でグループ化またはフィルター選択できます。|  
    |**インスタンスの状態**|メッセージを参照しているサービス インスタンスの状態です。 すべてのインスタンスの次の種類を検索することができますすべての実行中のインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンス、実行するための準備完了のインスタンス、スケジュール済みのインスタンス、再開不可のインスタンスが中断または一時停止、再開可能な状態。インスタンス。|  
    |**最大一致数**|一致項目の表示数を指定します。|  
    |**メッセージ ID**|メッセージをメッセージ ID でグループ化またはフィルター選択できます。|  
    |**メッセージの状態**|消費済み、処理中、中断、中断 (再開不可)、中断 (再開可能)、キューに登録済み、キューに登録済み (処理の待機中)、キューに登録済み (配信スケジュール済み)、およびキューに登録済み (再試行の待機中) の状態のメッセージを検索できます。|  
    |**メッセージの種類**|メッセージをメッセージの種類でグループ化またはフィルター選択できます。|  
    |**サービス クラス**|[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。|  
    |**サービス インスタンス ID**|メッセージをサービス インスタンス ID でグループ化またはフィルター選択できます。|  
    |**サービス名**|メッセージをサービス名でグループ化またはフィルター選択できます。|  
    |**サービスの種類 ID**|メッセージをサービスの種類 ID でグループ化またはフィルター選択できます。|  
    |**URI**|メッセージを URI でグループ化またはフィルター選択できます。|  
  
6.  完了、**値**で行う選択範囲の適切な列、**フィールド名**列です。  
  
7.  実行し、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**です。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)