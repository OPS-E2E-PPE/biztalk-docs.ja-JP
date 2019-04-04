---
title: Oracle データベースの変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ffabf27-7223-4473-b33e-af6f2990cb96
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd12434ab94d99dc7f002f1997d92f3ae5553981
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989691"
---
# <a name="receive-oracle-database-change-notifications"></a>Oracle データベースの変更通知を受け取る
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET データベース変更通知機能をサポートしています。 この機能を使用して、アダプター クライアントできます SELECT ステートメントとして登録データベースに対して、通知クエリし、データベースとしてアダプター クライアントを使用して、結果セットの SELECT ステートメントの変更の通知が送信されます。 データベースの変更通知は、OracleDependency クラスを使用して、アダプターに実装されます。 ODP.NET、および OracleDependency クラスのデータベース変更のサポート機能の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=124801](http://go.microsoft.com/fwlink/?LinkId=124801)を参照してください。  

 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]データベース変更通知をサポートするために、通知を受信する操作を公開します。 ただし、データベース変更通知を使用する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以下を確認する必要があります。  

- Oracle データベースの基になるバージョン 10.2 以降と Oracle データベースに接続します。 10.2 より前の oracle データベースのバージョンでは、通知はサポートされません。  

- 通知登録を作成する変更通知の特権を持つユーザーとして Oracle データベースに接続します。 ユーザーに変更通知の特権を付与するには、管理者特権を持つユーザーとして、Oracle データベースに接続し、SQL プロンプトで次のコマンドを実行します。  

  ```  
  grant change notification to <user name>  
  ```  

- Oracle データベースからデータベース変更通知を受信する ODP.NET で使用できる TCP ポートを決定します。 Windows ファイアウォール例外一覧には、TCP ポートを追加します。 Windows ファイアウォールの例外リストにポートを追加する方法については、[ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)を参照してください。 同じの TCP ポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。 バインディング プロパティの詳細については、[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)を参照してください。  

  一般的なデータベース変更通知を使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次が含まれます。  

1.  アダプターのクライアントを指定する必要があります`Notification`の受信の操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値をポーリングします。  

2.  アダプターのクライアントでのデータベース変更通知に登録する SQL SELECT ステートメントを指定する必要があります、 **NotificationStatement**プロパティをバインドします。 アダプターのクライアントは、として Oracle データベースからを使用して、結果セットの指定された SQL ステートメントの変更の通知を取得します。  

3.  アダプター クライアントは、リスナーで開始するとすぐに、アダプターがアダプター クライアントに通知を送信するかどうかを指定する必要があります、 **NotifyOnListenerStart**プロパティをバインドします。  

4.  通知としてアダプター クライアントに送信され、SELECT ステートメントがで指定された結果セットがの場合、 **NotificationStatement**プロパティのバインドが変更されました。  

> [!CAUTION]
>  Oracle データベースとアダプター クライアントの間のネットワークの停止がある場合、通知は送信されませんアダプター クライアントのネットワークの停止の期間中に Oracle データベースで行われた変更で、その後です。 したがって、重要なシナリオの通知の操作ではなく、ポーリング操作を使用する必要があります。  

## <a name="differences-between-notification-and-polling"></a>通知とポーリング間の違い  
 通知とポーリングは、両方の受信操作し、Oracle データベースでデータの変更について、アダプターをクライアントに通知、次の表は、2 つの間のいくつかの違いを示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  


|                                                                                                                              Notification                                                                                                                               |                                                                                                                                                                                                                                                      ポーリング                                                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                               通知は、Oracle database バージョン 10.2 に対してのみサポートされている以降です。                                                                                               |                                                                                                                                                                          サポートされているすべての Oracle データベース バージョンのポーリングがサポートされている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。                                                                                                                                                                           |
|                                                                                                          データの変更通知は瞬時では常にします。                                                                                                          | 一定の間隔でポーリングに使用できるデータを確認するポーリング間隔を構成するかまたは瞬時とタイミング データを使用します。 **ヒント:** ポーリングが継続的に、データの変更が発生したありと設定されるタイミングとしては、各変更の通知しないシナリオでスループットを向上を提供します。 代わりに、その後の前回の変更の通知以降に発生したすべての変更を通知するポーリング間隔を指定します。 |
| 通知は、Oracle データベースで開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セット内の変更がある場合は、通知を開始するように指示します。 通知は、Oracle データベースの機能です。 |                                                                                                                                         ポーリングは、アダプターによって開始されます。 アダプターは、データのポーリングに使用できるとポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証する SQL ステートメントを実行します。                                                                                                                                         |
|                                                                                             通知のステートメントを使用すると、Oracle データベースでデータを読み取るだけです。                                                                                             |                                                                                                                                                                                                                 ポーリング ステートメントを使用して、読み取りまたは Oracle データベース内のデータを更新することができます。                                                                                                                                                                                                                  |
|                                                                                   通知が、Insert などのデータの変更の種類にのみ通知は、更新、および削除します。                                                                                    |                                                                                                                                                                                                                            ポーリングには、実際のデータが変更されたことについて通知されます。                                                                                                                                                                                                                            |

 詳細については。  

- 通知操作に関連するバインドのプロパティを参照してください[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。  

- 通知の操作を使用する方法[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[受信 Oracle データベース変更通知を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)します。  

## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)