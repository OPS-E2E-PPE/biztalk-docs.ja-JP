---
title: Oracle データベースの変更通知を受け取る |Microsoft ドキュメント
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
ms.openlocfilehash: 1d1c33ef7bacf96a152d4b02d0c8c08991f96d64
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215658"
---
# <a name="receive-oracle-database-change-notifications"></a>Oracle データベースの変更通知を受信します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET データベースの変更通知機能をサポートします。 この機能を使用して、アダプター クライアントことができます、SELECT ステートメントとして登録、データベースに対する通知クエリし、アダプター クライアントとしてを使用して、SELECT ステートメントの変更の結果セットは、データベースが通知を送信します。 データベースの変更の通知は、OracleDependency クラスを使用して、アダプターで実装されます。 ODP.NET および OracleDependency クラスでのデータベース変更のサポート機能の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=124801](http://go.microsoft.com/fwlink/?LinkId=124801)です。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作を公開する受信、データベースの変更の通知をサポートするために、通知します。 ただし、データベースの変更通知を使用する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以下を確認する必要があります。  
  
-   Oracle データベースの基になるバージョン 10.2 またはそれ以降の Oracle データベースに接続します。 10.2 より前の oracle データベースのバージョンは、通知をサポートしていません。  
  
-   通知の登録を作成する変更通知特権を持つユーザーとして Oracle データベースに接続します。 特権を付与するには、変更通知をユーザーに、管理者特権を持つユーザーとして Oracle データベースに接続し、SQL プロンプトで次のコマンドを実行します。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   Oracle データベースからデータベースの変更通知を受け取る ODP.NET で使用できる TCP ポートを決定します。 Windows ファイアウォールの例外一覧に TCP ポートを追加します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)です。 同じ TCP ポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。 バインディング プロパティの詳細については、次を参照してください。[バインドのプロパティの使用](https://msdn.microsoft.com/library/dd788467.aspx)です。  
  
 一般的なデータベースの変更通知を使用して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次が含まれます。  
  
1.  アダプターのクライアントを指定する必要があります`Notification`で受信操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値をポーリングしています。  
  
2.  アダプターのクライアントが、SQL SELECT ステートメントでデータベースの変更通知を登録するを指定する必要があります、 **NotificationStatement**プロパティをバインドします。 アダプターのクライアントは、として Oracle データベースからを使用して、結果セットの指定された SQL ステートメントの変更の通知を取得します。  
  
3.  アダプターのクライアントがでリスナーを起動するとすぐに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定する必要があります、 **NotifyOnListenerStart**プロパティをバインドします。  
  
4.  としてアダプター クライアントに通知が送信され、SELECT ステートメントがで指定された結果セットがの場合、 **NotificationStatement**プロパティのバインドを変更します。  
  
> [!CAUTION]
>  Oracle データベースとアダプタのクライアント間でネットワーク障害がある場合、通知は送信されませんアダプター クライアントへのネットワークの停止の期間中に、Oracle データベースで行われる変更とそれ以降。 したがって、重要なシナリオの通知操作ではなくポーリング操作を使用する必要があります。  
  
## <a name="differences-between-notification-and-polling"></a>通知とポーリングの相違点  
 通知のポーリング、両方の受信操作とは、Oracle データベースでデータの変更について、アダプターをクライアントに通知を次の表は、2 つの間の違いを示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  
  
|Notification|ポーリング|  
|------------------|-------------|  
|通知は、Oracle データベース バージョン 10.2 に対してのみサポートされているおよびそれ以降です。|サポートされているすべての Oracle データベース バージョンのポーリングがサポートされている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|  
|データの変更通知は瞬時では常にします。|一定の間隔でポーリングの使用可能なデータを確認するポーリング間隔を構成するか、または瞬時に、そのデータが使用可能です。 **ヒント:** ポーリングすれば、スループットを向上させる、データの変更が、継続的に行われていると、発生したタイミングととしてそれぞれの変更の通知を受けるたくないシナリオでします。 代わりに、前回の変更通知以降に行われたすべての変更の通知されるようにすた後ポーリング間隔を指定します。|  
|通知は、Oracle データベースで開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セットの変更がある場合に通知を開始するように指示します。 通知は、Oracle データベースの機能です。|ポーリングは、アダプターによって開始されます。 アダプターでは、データのポーリングを使用し、ポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証する SQL ステートメントを実行します。|  
|通知のステートメントを使用すると、Oracle データベースでデータを読み取るだけです。|ポーリング ステートメントを使用して、読み取るまたは Oracle データベース内のデータを更新することができます。|  
|Insert などのデータ変更の種類のみ通知を通知は、更新、および削除します。|ポーリングでは、実際のデータが変更されたことについて通知されます。|  
  
 詳細については。  
  
-   通知操作に関連するバインドのプロパティを参照してください[バインドのプロパティの使用](https://msdn.microsoft.com/library/dd788467.aspx)です。  
  
-   通知の操作を使用する方法[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[受信 Oracle データベースの変更通知を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)