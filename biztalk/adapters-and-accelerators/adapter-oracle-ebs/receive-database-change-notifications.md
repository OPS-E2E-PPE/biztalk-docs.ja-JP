---
title: データベース変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be1eacf1-7fba-4eca-b35b-9770904d9ebd
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91bf169514d455b3f16800511557afba94fb321d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374768"
---
# <a name="receive-database-change-notifications"></a>データベース変更通知を受け取る
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ODP.NET データベース変更通知機能をサポートしています。 この機能を使用して、アダプター クライアントできます SELECT ステートメントとして登録データベースに対して、通知クエリし、データベースとしてアダプター クライアントを使用して、結果セットの SELECT ステートメントの変更の通知が送信されます。 データベースの変更通知は、OracleDependency クラスを使用して、アダプターに実装されます。 ODP.NET と OracleDependency クラスでのデータベース変更のサポート機能の Oracle 固有の詳細を参照してください[ http://go.microsoft.com/fwlink/p/?LinkId=124801](http://go.microsoft.com/fwlink/p/?LinkId=124801)します。  

## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データベース変更通知をサポートするために、通知を受信する操作を公開します。 ただし、データベース変更通知を使用する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以下を確認する必要があります。  

- Oracle データベースの基になるバージョン 10.2 以降では、Oracle E-business Suite に接続します。 10.2 より前の oracle データベースのバージョンでは、通知はサポートされません。  

- 通知登録を作成する変更通知の特権を持つユーザーとして Oracle E-business Suite に接続します。 ユーザーに変更通知の特権を付与するには、管理者特権を持つユーザーとして、Oracle データベースに接続し、SQL プロンプトで次のコマンドを実行します。  

  ```  
  grant change notification to <user name>  
  ```  

- Oracle データベースからデータベース変更通知を受信する ODP.NET で使用できる TCP ポートを決定します。 Windows ファイアウォール例外一覧には、TCP ポートを追加します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)します。 同じの TCP ポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。 バインディング プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  

  一般的なデータベース変更通知を使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次が含まれます。  

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
|                                                                                               通知は、Oracle database バージョン 10.2 に対してのみサポートされている以降です。                                                                                               |                                                                                                                                                                   サポートされているすべての Oracle データベース バージョンのポーリングがサポートされている、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。                                                                                                                                                                    |
|                                                                                                          データの変更通知は瞬時では常にします。                                                                                                          | 一定の間隔でポーリングに使用できるデータを確認するポーリング間隔を構成するかまたは瞬時とタイミング データを使用します。 **ヒント:** ポーリングすれば、スループットを向上させる継続的に、データの変更が行われていてと、発生したタイミングとしては、各変更の通知したくないです。 代わりに、その後の前回の変更の通知以降に発生したすべての変更を通知するポーリング間隔を指定します。 |
| 通知は、Oracle データベースで開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セット内の変更がある場合は、通知を開始するように指示します。 通知は、Oracle データベースの機能です。 |                                                                                                                                         ポーリングは、アダプターによって開始されます。 アダプターは、データのポーリングに使用できるとポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証する SQL ステートメントを実行します。                                                                                                                                         |
|                                                                                             通知のステートメントを使用すると、Oracle データベースでデータを読み取るだけです。                                                                                             |                                                                                                                                                                                                                 ポーリング ステートメントを使用して、読み取りまたは Oracle データベース内のデータを更新することができます。                                                                                                                                                                                                                  |
|                                                                                   通知が、Insert などのデータの変更の種類にのみ通知は、更新、および削除します。                                                                                    |                                                                                                                                                                                                                            ポーリングには、実際のデータが変更されたことについて通知されます。                                                                                                                                                                                                                            |

 詳細については。  

- 通知操作に関連するバインドのプロパティを参照してください[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  

- 通知の操作を使用する方法[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Reaceive データベース変更通知を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)します。  

## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)