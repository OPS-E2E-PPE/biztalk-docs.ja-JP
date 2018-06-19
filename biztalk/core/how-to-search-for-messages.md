---
title: メッセージを検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255282"
---
# <a name="how-to-search-for-messages"></a>メッセージを検索する方法
使用することができます、 **クエリ** メッセージの特定のクラスを検索するには、BizTalk Server 管理コンソールでタブをクリックします。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-messages"></a>メッセージを検索するには  
  
1.  をクリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], 、 をクリックし、 **BizTalk Server 管理コンソール**します。  
  
2.  コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3.  詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。  
  
4.  **クエリ式** グループの **値** 列で、選択 **メッセージ** ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |アイテム|Description|  
    |----------|-----------------|  
    |**作成日時**|指定した日時の前または後に作成されたメッセージを検索します。|  
    |**エラー アダプター**|グループ化することができますかアダプターの種類別にメッセージをフィルター処理: ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、または Windows SharePoint Services です。|  
    |**エラー コード**|メッセージをエラー コードでグループ化またはフィルター選択できます。|  
    |**エラーの説明**|メッセージをエラーの説明でグループ化またはフィルター選択できます。|  
    |**ホスト名**|メッセージをホスト名でグループ化またはフィルター選択できます。|  
    |**インスタンスの状態**|メッセージを参照しているサービス インスタンスの状態です。 すべてのインスタンスの次の種類を検索することができます。 すべての実行中のインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンス、すぐに実行インスタンス、スケジュール済みのインスタンス、中断、再開不可のインスタンスまたは一時停止、再開可能なインスタンス。|  
    |**最大一致数**|一致項目の表示数を指定します。|  
    |**メッセージ ID**|メッセージをメッセージ ID でグループ化またはフィルター選択できます。|  
    |**メッセージの状態**|消費済み、処理中、中断、中断 (再開不可)、中断 (再開可能)、キューに登録済み、キューに登録済み (処理の待機中)、キューに登録済み (配信スケジュール済み)、およびキューに登録済み (再試行の待機中) の状態のメッセージを検索できます。|  
    |**メッセージの種類**|メッセージをメッセージの種類でグループ化またはフィルター選択できます。|  
    |**サービス クラス**|[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。|  
    |**サービス インスタンス ID**|メッセージをサービス インスタンス ID でグループ化またはフィルター選択できます。|  
    |**サービス名**|メッセージをサービス名でグループ化またはフィルター選択できます。|  
    |**サービスの種類 ID**|メッセージをサービスの種類 ID でグループ化またはフィルター選択できます。|  
    |**URI**|メッセージを URI でグループ化またはフィルター選択できます。|  
  
6.  完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。  
  
7.  完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)