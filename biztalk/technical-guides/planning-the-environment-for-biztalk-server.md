---
title: "BizTalk server 環境のプランニング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e9ef0b4-eccb-47e2-bbb5-e859ffa0468c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66cd358f3d8a4fbda2c4ed43432f1ad8b2f6979e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-the-environment-for-biztalk-server"></a>BizTalk server 環境のプランニング
Operations guide の「の計画セクションには、役割と責任に関連付けられているがについて説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 計画に関する推奨事項のアプリケーションおよびデータ層が含まれている、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびその計画推奨事項を提供、リリースの BizTalk ソリューションの管理の段階です。  
  
 メッセージが再生としては、"計画フェールオーバーすると、する予定の場合は失敗します"。 セージこのアドバイスに例外が確かに、実稼働の BizTalk ソリューションの正常な実装はありませんうちの 1 つ。 計画に関するセクションに、この概要トピックでは、BizTalk ソリューションを計画する際にする必要があります意思決定の大まかな概要を説明します。  
  
## <a name="deciding-whether-biztalk-server-is-the-right-tool-for-the-job"></a>BizTalk Server がジョブの適切なツールであるかどうかを判断します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]「ビジネス統合エンジン」と見なすことができます。 基本的に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]多種多様な業務システム、プロセス、およびメッセージを統合するよう設計されています。 たとえば、EDI 標準に準拠するメッセージを交換するビジネス システムは、RosettaNet 標準に準拠するメッセージを交換するビジネス システムと統合する必要があります。 または、SAP を使用する内部ビジネス システムは、Microsoft SQL Server データベースにデータを格納する別の内部ビジネス システムと通信する必要があります。 または、おそらくのみを送信したり、FTP プロトコルを使用してメッセージを受信するビジネス システムは、HTTP プロトコルを使うことができますのみビジネス システムとメッセージを交換する必要があります。 します。  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム間でメッセージ配信のための仲介者として動作することにより、このようなさまざまなシステムの統合に対応します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]さまざまな業界標準トランスポート プロトコル、ドキュメントの交換形式、および基幹業務アプリケーションをサポートしています。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]また、BizTalk オーケストレーション エンジンで強力なビジネス プロセスの自動化機能を提供します。 BizTalk オーケストレーション エンジンで実行される実行可能コードに作成できるビジネス プロセスの図式を作成するのにには、BizTalk オーケストレーション デザイナーを使用します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インフォメーション ワーカーがビジネス アクティビティ監視 (BAM) などのメッセージ ワークフロー エンジン、ビジネス ルール エンジン (BRE)、およびテクノロジを含むビジネスの統合を容易にするその他のいくつかの機能も含まれています。  
  
 使用しての詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス プロセス管理機能を参照してください[ホワイト ペーパー: Microsoft と BPM — の技術概要](http://go.microsoft.com/fwlink/?LinkId=106015)(http://go.microsoft.com/fwlink/?LinkId=106015)。 経由で他のいずれかが利点と Microsoft によって提供されるさまざまな統合テクノロジに関する詳細についてを参照してください。 [Microsoft 統合テクノロジを理解する](http://go.microsoft.com/fwlink/?LinkId=158452)(http://go.microsoft.com/fwlink/?LinkId=158452)。  
  
 特定の統合のシナリオは、他のマイクロソフト製品に適しています。 次のシナリオのいずれかによって、プライマリ フォーカスがある場合は、代わりにこれらの Microsoft 製品の使用を検討[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
|**Scenario**|**製品を使用するには**|  
|------------------|------------------------|  
|ユーザー プロビジョニングの構成|**Microsoft Identity Lifecycle Manager 2010**<br /><br /> Microsoft Identity Lifecycle Manager 2010 の詳細については、次を参照してください。 [Microsoft Identity Lifecycle Manager 2010 FP1](http://go.microsoft.com/fwlink/?LinkId=204577) (http://go.microsoft.com/fwlink/?LinkId=204577)。|  
|システム間でデータのレプリケーション|**SQL Server のレプリケーション**<br /><br /> SQL Server レプリケーションの詳細については、次を参照してください。 [SQL Server 2008 R2 レプリケーション](http://go.microsoft.com/fwlink/?LinkID=69978)(http://go.microsoft.com/fwlink/?LinkID=69978)。|  
|データの抽出、変換、および読み込み (ETL)|**SQL Server Integration Services (SSIS)**<br /><br /> SQL Server Integration Services の詳細については、次を参照してください。 [SQL Server 2008 R2 Integration Services](http://go.microsoft.com/fwlink/?LinkId=152044) (http://go.microsoft.com/fwlink/?LinkId=152044)。|  
  
## <a name="deciding-which-edition-of-biztalk-server-is-right-for-the-job"></a>BizTalk Server のエディションは、ジョブの右側を決定します。  
 特定のシナリオを対象とする各 BizTalk Server の 4 つの異なるエディションがあります。 BizTalk Server の 4 つのエディションは次のとおりです。  
  
-   **エンタープライズ**- 高ボリューム、信頼性、および可用性のエンタープライズ レベルの要件と顧客に設計されています。  
  
-   **標準的な**- 中程度のボリュームと配置の小数点以下桁数の要件を企業に設計されています。  
  
-   **ブランチ**の特別なバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ハブ用に設計され、スポーク RFID を含む展開シナリオです。  
  
-   **開発者**- 開発およびテストのすべての Enterprise Edition の機能を提供し、評価目的に無償で BizTalk Server の評価版として使用されます。 評価版としてインストールされているときに BizTalk Server は 120 日間機能します。  
  
-   **RFID エンタープライズ**- の BizTalk RFID Server と BizTalk RFID Mobile を開発、配置、および豊富な RFID およびセンサ ソリューションの管理に含まれて、拡張性の高いプラットフォームを提供するよう設計されています。  
  
 BizTalk Server のさまざまなエディションの詳細については、次を参照してください。 [Microsoft BizTalk Server のエディション](http://go.microsoft.com/fwlink/?LinkId=108051)(http://go.microsoft.com/fwlink/?LinkId=108051)。  
  
## <a name="planning-for-message-load"></a>メッセージの読み込みの計画  
 あることを確認後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を満たしている、ビジネスの統合機能が必要、処理する BizTalk ソリューションとなるメッセージの読み込みが必要かを決定する必要がある次のことです。 これは、ためにの重要な決定事項のさまざまなエディション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スケール アップおよびスケール アウト機能が異なります。  
  
 メッセージの読み込みを確認するキーの負荷が最大持続可能なスループット (MST) と、最大持続可能な追跡スループット (MSTT)、BizTalk ソリューションを確認するテストを実行を開始します。 最大のスループット、および一般的なパフォーマンスのベスト プラクティスの測定の詳細については、次を参照してください。、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
## <a name="planning-for-expansion"></a>展開の計画  
 Enterprise edition を使用して BizTalk ソリューションの実装の検討[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]多数の取引先を追加する場合は必要があるホスト クラスタ リングを使用するか、する必要がありますを実行している複数のコンピューターにスケール アウト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、BizTalk グループです。 Standard、およびブランチ エディション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を実行している複数のコンピューターには適応できない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループまたはホスト クラスタ リングでします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server のロールと責任](../technical-guides/biztalk-server-roles-and-responsibilities.md)  
  
-   [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)  
  
-   [データベース階層の計画](../technical-guides/planning-the-database-tier.md)  
  
-   [開発、テスト、ステージング、および製品環境の計画](../technical-guides/planning-the-development-testing-staging-and-production-environments.md)