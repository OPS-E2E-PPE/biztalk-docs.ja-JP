---
title: BizTalk Server を使用して Oracle E-business Suite データベースの変更通知を受け取る |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e92520cf-c552-4225-abba-8e03f73ecf70
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24ac132f599256c2051763ed849e4e5329563201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215682"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-biztalk-server"></a>BizTalk Server を使用して Oracle E-business Suite データベースの変更通知を受信します。
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite からデータベースの変更の通知メッセージを受信します。 Oracle E-business Suite での通知に対して、アダプターの登録に使用する SELECT ステートメントを指定することができます。 通知の登録、SELECT ステートメントの結果セットが変更されたときに通知メッセージを受信します。 アダプターで通知をサポートする方法の詳細については、次を参照してください。[データベースの変更通知の受信、Oracle E-business Suite アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)です。  
  
 次に、いくつかのシナリオを構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite から通知を受け取る。  
  
-   アダプターのクライアントは、最後の通知以降、データベース テーブルに加えられた変更についてのみなど「インクリメント」の通知のみを取得します。  
  
-   データベース テーブルには、大量の行が挿入される、アダプターのクライアントは複数を構成できます受信通知の負荷を分散する場所を受信します。  
  
 アダプターのクライアントには、通知メッセージが表示される後の受信通知の種類に基づいて特定のタスクを実行できます。 たとえば、このような形で実行される挿入の通知を受信した場合のタスクの 1 つのセットと別の一連のタスクの更新通知を受信した場合、BizTalk オーケストレーションを設計できます。  
  
> [!CAUTION]
>  Oracle データベースとアダプタのクライアント間でネットワーク障害がある場合、通知は送信されませんアダプター クライアントへのネットワークの停止の期間中に、Oracle データベースで行われる変更とそれ以降。 したがって、重要なシナリオの通知操作ではなくポーリング操作を使用する必要があります。  
  
 このセクションのトピックでは、これらの各シナリオのアダプターを構成する方法について説明します。 Oracle E-business Suite を使用してからの通知の取得を開始する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、特定のバインディング プロパティを指定する必要があります。 通知に関連するバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 通知メッセージの構造に関する詳細については、次を参照してください。[通知操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)です。  
  
 Oracle E-business Suite から通知を受信するためには、ことを確認してください。  
  
-   サポートされている Oracle データベースのバージョンに接続するには、アダプターを使用します。 10.2 より前の oracle データベースのバージョンは、通知をサポートしていません。  
  
-   **変更通知**特権は、データベースの変更通知を受信するために必要です。  この特権を構成するのに管理者特権を使用して Oracle データベースに接続し、SQL のプロンプトで次のコマンドを入力します。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   使用して Oracle データベースからデータベースの変更通知を受信する ODP.NET する TCP ポートで決定します。 Windows ファイアウォールの例外リストにそのポートを追加します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)です。 同じポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。 バインディング プロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [データベースの変更通知の受信、Oracle E-business Suite アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)  
  
-   [Oracle E-business Suite で特定のタスクを完了する通知メッセージの処理](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)  
  
-   [BizTalk Server を使用して増分値 Oracle E-business Suite の変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [Oracle E-business Suite データベースの変更通知の複数受信場所が表示されます。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [後の Oracle E-business Suite データベース変更通知を受信する受信場所の内訳](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md)  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)