---
title: 'チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成する |Microsoft Docs'
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
ms.openlocfilehash: 4dca1edae471c7d0bb588c4d9dc45168a4f66a2c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007987"
---
# <a name="tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013"></a>チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。
ここでは、[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が関連するハイブリッド アプリケーションを作成する方法の手順について説明します。  

## <a name="business-scenario"></a>ビジネス シナリオ  
 Northwind は取引先からフラット ファイル EDI メッセージの形式で販売注文を受けている企業であり、取引先の 1 社が Contoso です。 Northwind は、次のことを行うエンド ツー エンドのアプリケーションをセットアップしたいと考えています。  

- **EDI メッセージの処理を管理**– アプリケーションのこのモジュールでは、Contoso から受信したメッセージを標準の EDI メッセージ形式に準拠していることを確認する必要があります。 また、メッセージが正常に処理されたことを検証するために必要なすべての確認を生成する必要もあります。  

- **データを処理するビジネス ロジックを使用して**– EDI メッセージは正常に検証され、処理、Northwind がさらに処理するためのビジネス ロジックに対してメッセージを実行する必要があります。 たとえば、受信メッセージの注文数量が特定の数量を超えている場合、データは SQL Server データベースに格納され、 それ以外の場合は共有ファイルの場所に送信されるなどです。  

  Northwind は、このシナリオを実現するため、EDI メッセージ処理がクラウド上で実行され、ビジネス ロジックによるデータ処理が社内で実行されるようにするハイブリッド アプリケーションをセットアップすることに決定しました。 Northwind は、このハイブリッド アプリケーションをセットアップするために、次のものを使用します。  

- **[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]**  – Azure BizTalk ポータルで使用可能な[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]で取引先パートナーとの EDI 契約を構成できるように[!INCLUDE[winazure](../includes/winazure-md.md)]します。 Northwind は 2012 年 4 月リリースの [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] を使用して、受信 EDI メッセージを処理し、X12 840 販売注文スキーマに対してメッセージを検証し、Northwind で必要なスキーマに変換してから Service Bus キューに送信するアグリーメントを作成して展開します。 したがって、ハイブリッド アプリケーションを開発するため、データは Service Bus キューから社内アプリケーションに送信される必要があります。  

- **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  – Service Bus の新しいアダプター (**Sb-messaging**) で使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]により、アプリケーションは、という具合にキュー、トピックなどの Service Bus エンティティからメッセージを受信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 一部として、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Northwind 使用して、アプリケーション、オーケストレーションに受信した販売注文の数量が 100 より大きいかどうかを判断します。 メッセージがという名前の SQL Server データベース テーブルに挿入された数量が 100 を超える場合、 **SalesOrder**します。 この数量が 100 以下の場合、メッセージは共有ファイルの場所に送信されます。  

   Northwind は、メッセージを SQL Server データベース テーブルに挿入するために、[!INCLUDE[adaptersql](../includes/adaptersql-md.md)] の一部として利用可能な [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] を使用します。  

### <a name="end-to-end-message-flow"></a>エンド ツー エンドのメッセージ フロー  
 ハイブリッド アプリケーションでのメッセージのフローは次のとおりです。  

1. Contoso は X12 販売注文メッセージをエンドポイントに送信します。エンドポイントでは、クラウド上に EDI アグリーメントが展開されています。  

2. メッセージが正しく EDI アグリーメントを通じて処理されると、Service Bus キューに送信されます。  

3. SB-Messaging 受信アダプターは Service Bus キューからのメッセージを処理し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に展開されているオーケストレーションをインスタンス化して、注文数量に基づいて異なる送信先にメッセージを送信します。  

4. 注文数量が 100 より大きい、オーケストレーションがメッセージを挿入、 **SalesOrder**テーブル。 注文数量が 100 以下の場合、メッセージは共有ファイルの場所に書き込まれます。  

## <a name="set-up-your-computer"></a>コンピューターのセットアップ  
 このチュートリアルでは、4 つの広範なアクティビティを実行する必要があります。 次の表に、各アクティビティとそのソフトウェア要件を示します。  


|                                                            アクティビティ                                                             |                                                                                                                                              必要なソフトウェア                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                     EDI アグリーメントに必要な EDI アイテムを作成する                                     | このチュートリアルは、2012 年 4 月リリースの [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] と、X12 840 販売注文スキーマを使用して作成されました。 これらからダウンロードできます。 [ http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)します。 |
|                                               EDI アグリーメントを作成して展開する                                               |                                                                                 EDI アグリーメントは Azure で展開されるので、Azure BizTalk Portal にログインするために必要なものは Web ブラウザー (Internet Explorer など) のみです。                                                                                  |
| [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを作成、展開、および構成する |              プロビジョニングする場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にある指示に従って、Azure VM 上のコンピューター [ http://msdn.microsoft.com/library/azure/jj248689.aspx](http://msdn.microsoft.com/library/azure/jj248689.aspx)します。               |
|                                        EDI アグリーメント エンドポイントにテスト メッセージを送信する                                        |   [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] に同梱のサンプル パッケージにある MessageSender ツールを使用できます。 サンプル パッケージをダウンロードする[ http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)します。   |

 これらはすべて同じコンピューターにインストールすることも、別のコンピューターにインストールすることもできます。  

## <a name="in-this-section"></a>このセクションの内容  

-   [手順 1 (Azure 用): EDI プロジェクトを作成する](../core/step-1-for-azure-create-the-edi-project.md)  

-   [手順 2 (Azure 用): EDI アグリーメントを作成する](../core/step-2-for-azure-create-an-edi-agreement.md)  

-   [手順 3 (Azure 用): Service Bus キューを作成する](../core/step-3-for-azure-create-a-service-bus-queue.md)  

-   [手順 4 (オンプレミス): SQL Server テーブルを作成する](../core/step-4-on-premises-create-the-sql-server-table.md)  

-   [手順 5 (オンプレミス): SalesOrder テーブルにメッセージを挿入するためのスキーマを生成する](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)  

-   [手順 6 (オンプレミス): キューから Insert スキーマにメッセージをマップする変換を作成する](../core/step-6-map-the-message-from-the-queue-to-the-insert-schema.md)  

-   [手順 7 (オンプレミス): オーケストレーションを作成する](../core/step-7-on-premises-create-an-orchestration.md)  

-   [手順 8 (オンプレミス): BizTalk Server アプリケーションを構成する](../core/step-8-on-premises-configure-the-biztalk-server-application.md)  

-   [手順 9: ソリューションのテスト](../core/step-9-test-the-solution.md)