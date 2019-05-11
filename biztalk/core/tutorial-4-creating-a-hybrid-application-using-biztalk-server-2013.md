---
title: チュートリアル 4:BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a9de95f-7d2c-437d-be5b-0062592f32c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82d3f7a9b8cb4a59cf0be2d409a80004e8e5c504
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399186"
---
# <a name="tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013"></a>チュートリアル 4:BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。
このセクションで必要とするハイブリッド アプリケーションを作成する方法の詳細なチュートリアルを提供します[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

## <a name="business-scenario"></a>ビジネス シナリオ  
 Northwind のパートナーは、それらのいずれかから販売注文を受けている企業は、フラット ファイル EDI メッセージの形式で、Contoso をされています。 Northwind は以下では、次のエンド ツー エンド アプリケーションを設定する必要があります。  

- **EDI メッセージの処理を管理**– アプリケーションのこのモジュールでは、Contoso から受信したメッセージを標準の EDI メッセージ形式に準拠していることを確認する必要があります。 このモジュールは、メッセージが正常に処理されたことを確認する必要なすべての受信確認を生成もする必要があります。  

- **データを処理するビジネス ロジックを使用して**– EDI メッセージは正常に検証され、処理、Northwind がさらに処理するためのビジネス ロジックに対してメッセージを実行する必要があります。 たとえば、受信したメッセージの注文数量が特定の時間より長い場合は、SQL Server データベースにデータが格納されます。 それ以外の場合、データは、共有ファイルの場所に送信されます。  

  このシナリオを実現するためには、Northwind は、EDI メッセージの処理は、クラウド上で行われますビジネス ロジックによるデータの処理が社内で実行中に、ハイブリッド アプリケーションをセットアップする決定します。 このハイブリッドを設定するには、Northwind アプリケーションは、次の。  

- **[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]**  – Azure BizTalk ポータルで使用可能な[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]で取引先パートナーとの EDI 契約を構成できるように[!INCLUDE[winazure](../includes/winazure-md.md)]します。 Northwind は、 [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] – 2012 年 4 月リリースを作成し、受信 EDI メッセージを処理、X12 840 販売注文スキーマ、変換、メッセージのスキーマには、Northwind で必要なし、メッセージを送信と照らし合わせて検証するアグリーメントをデプロイするにはService Bus のキュー。 そのため、ハイブリッド アプリケーションを開発するする必要がありますからデータを送信、Service Bus キューをオンプレミス アプリケーションにします。  

- **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  – Service Bus の新しいアダプター (**Sb-messaging**) で使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]により、アプリケーションは、という具合にキュー、トピックなどの Service Bus エンティティからメッセージを受信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 一部として、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Northwind 使用して、アプリケーション、オーケストレーションに受信した販売注文の数量が 100 より大きいかどうかを判断します。 メッセージがという名前の SQL Server データベース テーブルに挿入された数量が 100 を超える場合、 **SalesOrder**します。 数量が 100 未満の場合、メッセージは、共有ファイルの場所に送信されます。  

   Northwind を使用して SQL Server データベース テーブルにメッセージを挿入するのには、[!INCLUDE[adaptersql](../includes/adaptersql-md.md)]として使用できるの一部、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  

### <a name="end-to-end-message-flow"></a>エンド ツー エンド メッセージ フロー  
 これは、ハイブリッド アプリケーションでのメッセージのフローです。  

1. Contoso に送信する X12 販売注文メッセージを EDI アグリーメントがクラウドに配置される場所のエンドポイントにします。  

2. メッセージの EDI アグリーメントを通じて処理が正常に、Service Bus のキューに送信されます。  

3. Sb-messaging 受信アダプターは、Service Bus キューからメッセージを使用およびにデプロイされているオーケストレーションをインスタンス化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]注文数量に基づいて異なる送信先にメッセージを送信します。  

4. 注文数量が 100 より大きい、オーケストレーションがメッセージを挿入、 **SalesOrder**テーブル。 注文数量が 100 未満の場合は、メッセージは、共有ファイルの場所に書き込まれます。  

## <a name="set-up-your-computer"></a>コンピューターをセットアップします。  
 このチュートリアルでは、次の 4 つの広範なアクティビティを実行する必要があります。 次の表は、アクティビティとアクティビティごとのソフトウェアの要件を示します。  


|                                                            アクティビティ                                                             |                                                                                                                                              必要なソフトウェア                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                     EDI アグリーメントに必要な EDI アーティファクトを作成します。                                     | このチュートリアルで作成された、 [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] – 2012 年 4 月リリースと、X12 840 販売注文スキーマ。 これらからダウンロードできます。 [ http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)します。 |
|                                               作成して、EDI アグリーメントの展開                                               |                                                                                 Azure 上で EDI アグリーメントが展開されている、ためには、のみ、Web ブラウザー (Internet Explorer など)、Azure BizTalk Portal にログインする必要があります。                                                                                  |
| ビルド、配置、および構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション |              プロビジョニングする場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にある指示に従って、Azure VM 上のコンピューター [ http://msdn.microsoft.com/library/azure/jj248689.aspx](http://msdn.microsoft.com/library/azure/jj248689.aspx)します。               |
|                                        EDI アグリーメント エンドポイントにテスト メッセージを送信します。                                        |   パッケージに付属のサンプルで使用可能な MessageSender ツールを使用して[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]します。 サンプル パッケージをダウンロードする[ http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)します。   |

 これらはすべて、同じコンピューターまたは別のコンピューターにインストールすることができます。  

## <a name="in-this-section"></a>このセクションの内容  

-   [手順 1 (Azure 用):EDI プロジェクトを作成します。](../core/step-1-for-azure-create-the-edi-project.md)  

-   [手順 2 (Azure 用):EDI アグリーメントを作成します。](../core/step-2-for-azure-create-an-edi-agreement.md)  

-   [手順 3 (Azure 用):Service Bus キューを作成します。](../core/step-3-for-azure-create-a-service-bus-queue.md)  

-   [手順 4 (オンプレミス):SQL Server のテーブルを作成します。](../core/step-4-on-premises-create-the-sql-server-table.md)  

-   [手順 5 (オンプレミス):メッセージする SalesOrder テーブルを挿入するためのスキーマを生成します。](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)  

-   [手順 6 (オンプレミス):キューから Insert スキーマにメッセージをマップする変換を作成します。](../core/step-6-map-the-message-from-the-queue-to-the-insert-schema.md)  

-   [手順 7 (オンプレミス):オーケストレーションの作成](../core/step-7-on-premises-create-an-orchestration.md)  

-   [手順 8 (オンプレミス):BizTalk Server アプリケーションを構成します。](../core/step-8-on-premises-configure-the-biztalk-server-application.md)  

-   [手順 9:ソリューションをテストします。](../core/step-9-test-the-solution.md)