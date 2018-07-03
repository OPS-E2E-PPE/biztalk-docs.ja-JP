---
title: BizTalk Server を使用して Oracle E-business Suite データベース変更通知の受信 |Microsoft Docs
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
ms.openlocfilehash: 6381e2c429763596e3aa5c1fd70619cae588b68d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991427"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-biztalk-server"></a>BizTalk Server を使用して Oracle E-business Suite データベース変更通知を受信します。
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite からデータベース変更通知のメッセージを受信します。 Oracle E-business Suite を使用した通知に対して、アダプターの登録に使用する SELECT ステートメントを指定することができます。 登録通知の場合、SELECT ステートメントの結果セットが変更されたときに通知メッセージを受信します。 アダプターが通知をサポートする方法の詳細については、次を参照してください。[データベース変更通知の受信、Oracle E-business Suite アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)します。  
  
 構成することがいくつかのシナリオを次に、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite から通知を受け取ります。  
  
- アダプター クライアントの最後の通知以降、データベース テーブルに加えられたこれらの変更だけなど「インクリメント」の通知のみを取得します。  
  
- アダプター クライアントが複数を構成する場合は、データベース テーブルに多数の行を挿入して、受信負荷分散通知を受信する場所。  
  
  アダプター クライアントは、通知メッセージを受信、受信した通知の種類に基づいて特定のタスクを実行できます。 たとえばが実行される挿入の通知を受信した場合、タスクの 1 つのセットと別の一連のタスク、更新通知を受信した場合は、このような方法で、BizTalk オーケストレーションを設計できます。  
  
> [!CAUTION]
>  Oracle データベースとアダプター クライアントの間のネットワークの停止がある場合、通知は送信されませんアダプター クライアントのネットワークの停止の期間中に Oracle データベースで行われた変更で、その後です。 したがって、重要なシナリオの通知の操作ではなく、ポーリング操作を使用する必要があります。  
  
 このセクションのトピックでは、これらの各シナリオのアダプターを構成する方法について説明します。 Oracle E-business Suite を使用してからの通知の取得を開始する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、特定のバインド プロパティを指定する必要があります。 通知に関連するバインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 通知メッセージの構造に関する詳細については、次を参照してください。[通知操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)します。  
  
 Oracle E-business Suite から通知を受信することを確認します。  
  
-   サポートされている Oracle データベースのバージョンに接続するには、アダプターを使用します。 10.2 より前の oracle データベースのバージョンでは、通知はサポートされません。  
  
-   **変更通知**特権は、データベース変更通知を受信するために必要です。  この特権を構成するには、管理者特権を使用して Oracle データベースに接続し、SQL プロンプトで次のコマンドを入力します。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   Oracle データベースからデータベース変更通知を受信するために使用する ODP.NET する TCP ポートで決定します。 Windows ファイアウォールの例外リストには、そのポートを追加します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)します。 同じポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。 バインディング プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [データベース変更通知の受信、Oracle E-business Suite アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)  
  
-   [Oracle E-business Suite で特定のタスクを完了する通知メッセージの処理](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)  
  
-   [段階的に BizTalk Server を使用して Oracle E-business Suite の変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [Oracle E-business Suite データベース変更通知を複数受信場所の受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [後の Oracle E-business Suite データベース変更通知を受信する受信場所のブレーク ダウン](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md)  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)