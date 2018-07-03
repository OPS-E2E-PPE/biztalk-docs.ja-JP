---
title: BizTalk server 環境のプランニング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e9ef0b4-eccb-47e2-bbb5-e859ffa0468c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92039b397053d24909d6ade75797c9f68d06172
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977739"
---
# <a name="planning-the-environment-for-biztalk-server"></a>BizTalk server 環境のプランニング
操作ガイドの計画セクションには、役割と責任に関連付けられているがについて説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 アプリケーションとデータ層の推奨事項を計画が含まれますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびこれにより、リリースの計画に関する推奨事項が BizTalk ソリューションの管理ステージ提供します。  
  
 メッセージとしては、「計画しないと、する場合は失敗します」。 Sage のアドバイスはこの例外は確かにありますが、運用環境の BizTalk ソリューションの実装を成功させるないうち 1 つ。 この概要のトピックで、計画セクションには、BizTalk ソリューションを計画するときにする必要がありますの決定事項の概要を提供します。  
  
## <a name="deciding-whether-biztalk-server-is-the-right-tool-for-the-job"></a>BizTalk Server がジョブに適したツールであるかどうかを決める  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 「ビジネスの統合エンジン」として考えることができます。 基本的には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]さまざまなビジネス システム、プロセス、およびメッセージの統合には設計されています。 たとえば、EDI 標準に準拠するメッセージを交換するビジネス システムが RosettaNet の標準に準拠するメッセージを交換するためのビジネス システムと統合する必要があります。 または、SAP を使用する内部のビジネス システムは、Microsoft SQL Server データベースにデータを格納する別の社内ビジネス システムと通信する必要があります。 または、おそらく、のみを送信または FTP プロトコルを使用してメッセージを受信できるビジネス システムがビジネス システムが HTTP プロトコルのみを使用できるメッセージを交換する必要があります。  
  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] システム間のメッセージ配信の仲介者として機能することによって、このような異種システムの統合に対応します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] さまざまな業界標準のトランスポート プロトコル、ドキュメントの交換形式、および基幹業務アプリケーションをサポートしています。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] また、BizTalk オーケストレーション エンジンで強力なビジネス プロセスの自動化機能を提供します。 BizTalk オーケストレーション エンジンで実行される実行可能コードに組み込むことができるビジネス プロセスの視覚的な表現を作成するのにには、BizTalk オーケストレーション デザイナーを使用します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インフォメーション ワーカーがビジネス アクティビティ監視 (BAM) などのメッセージのワークフロー エンジン、ビジネス ルール エンジン (BRE)、およびテクノロジを含む、ビジネスの統合を容易にするその他のいくつかの機能も含まれています。  
  
 使用しての詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス プロセス管理の機能を参照してください[ホワイト ペーパー: Microsoft と BPM: 技術概要](http://go.microsoft.com/fwlink/?LinkId=106015)(<http://go.microsoft.com/fwlink/?LinkId=106015>)。 Microsoft と、もう一方が 1 つの利点がありますから提供されるさまざまな統合テクノロジの詳細については、次を参照してください。[について Microsoft の統合テクノロジ](http://go.microsoft.com/fwlink/?LinkId=158452)(<http://go.microsoft.com/fwlink/?LinkId=158452>)。  
  
 特定の統合のシナリオは、他のマイクロソフト製品に適しています。 時に、次のシナリオのいずれかの主な目的は、の場合は、代わりにこれらの Microsoft 製品の使用を検討[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
|**Scenario**|**製品を使用するには**|  
|------------------|------------------------|  
|ユーザー プロビジョニング|**Microsoft Identity Lifecycle Manager 2010**<br /><br /> Microsoft Identity Lifecycle Manager 2010 の詳細については、次を参照してください。 [Microsoft Identity Lifecycle Manager 2010 FP1](http://go.microsoft.com/fwlink/?LinkId=204577) (http://go.microsoft.com/fwlink/?LinkId=204577)します。|  
|システム間でデータのレプリケーション|**SQL Server のレプリケーション**<br /><br /> SQL Server レプリケーションの詳細については、次を参照してください。 [SQL Server 2008 R2 レプリケーション](http://go.microsoft.com/fwlink/?LinkID=69978)(http://go.microsoft.com/fwlink/?LinkID=69978)します。|  
|データの抽出、変換、および読み込み (ETL)|**SQL Server Integration Services (SSIS)**<br /><br /> SQL Server Integration Services の詳細については、次を参照してください。 [SQL Server 2008 R2 Integration Services](http://go.microsoft.com/fwlink/?LinkId=152044) (http://go.microsoft.com/fwlink/?LinkId=152044)します。|  
  
## <a name="deciding-which-edition-of-biztalk-server-is-right-for-the-job"></a>BizTalk Server のエディションは、ジョブの権利を決定します。  
 BizTalk Server の特定のシナリオは対象としてそれぞれの 4 つの異なるエディションがあります。 BizTalk Server の 4 つのエディションは次のとおりです。  
  
- **エンタープライズ**高ボリューム、信頼性、および可用性のエンタープライズ レベルの要件を持つお客様向けに設計します。  
  
- **標準**中程度のボリュームと展開のスケールの要件を企業向けに設計します。  
  
- **ブランチ**の専門分野のバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]向けのハブとスポークの展開シナリオを含む RFID します。  
  
- **開発者**- 開発およびテスト目的ですべての Enterprise Edition の機能を提供し、評価のためのコストなしで、BizTalk Server の評価版として使用されます。 評価版としてインストールすると、BizTalk Server は 120 日間機能します。  
  
- **RFID Enterprise** - BizTalk RFID Server および BizTalk RFID Mobile に開発、展開、および多機能な RFID およびセンサ ソリューションでは、管理が含まれています、拡張性の高いプラットフォームを提供するよう設計されています。  
  
  BizTalk Server のさまざまなエディションの詳細については、次を参照してください。 [Microsoft BizTalk Server のエディション](http://go.microsoft.com/fwlink/?LinkId=108051)(http://go.microsoft.com/fwlink/?LinkId=108051)します。  
  
## <a name="planning-for-message-load"></a>メッセージの読み込みの計画  
 あると判断されたら[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス統合ニーズ、次の点を処理する BizTalk ソリューションとなるメッセージの読み込みが必要かを判断する必要があります。 これは、ためにの重要な決断のさまざまなエディション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スケール アップおよびスケール アウト機能が異なります。  
  
 メッセージの負荷を決定するキーでは、最大持続可能なスループット (MST) と、最大持続可能な追跡スループット (MSTT) の BizTalk ソリューションを特定のロード テストを実行します。 最大持続可能スループット、および一般的なパフォーマンスのベスト プラクティスの測定の詳細については、次を参照してください。、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)します。  
  
## <a name="planning-for-expansion"></a>展開の計画  
 Enterprise edition を使用して BizTalk ソリューションの実装を検討[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]場合非常に多くの取引先パートナーを追加する必要がありますを使用して、ホスト クラスタ リング、またはがする必要を実行している複数のコンピューターへのスケール アウト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、BizTalk グループ。 Standard および Branch エディション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を実行している複数のコンピューターに対応していません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループまたはホスト クラスタ リングします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server のロールと責任](../technical-guides/biztalk-server-roles-and-responsibilities.md)  
  
-   [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)  
  
-   [データベース階層の計画](../technical-guides/planning-the-database-tier.md)  
  
-   [開発、テスト、ステージング、および製品環境の計画](../technical-guides/planning-the-development-testing-staging-and-production-environments.md)