---
title: "データベースのパフォーマンスの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7212fa37-88e0-4b5f-af97-c72063357645
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1338088acc91a45572ae1b49131d99f6c58cb739
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-performance"></a>データベースのパフォーマンスの計画
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、非常に高くデータベース処理を要するアプリケーションで Microsoft 最大 13 個の独立したデータベースを作成することがあります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 データベース処理を要するの性質[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、適切なバージョンとエディションを選択する重要な要素は[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 実行しているコンピューターのパフォーマンスを最適化するために[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]そのハウス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース」を参照し、推奨事項に従い、 [BizTalk Server データベースの最適化](http://go.microsoft.com/fwlink/?LinkID=101578)ホワイト ペーパー ([http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578))。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]どちらのデータベースをインストールする必要があります[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]または[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]です。  
  
> [!NOTE]  
>  このホワイト ペーパーが他のバージョンの書き込み中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、に対して同じ推奨事項を使用する[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  / [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]です。  
  
## <a name="considerations-for-sql-server-editions"></a>SQL Server のエディションに関する考慮事項  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースは、できるだけ専用の SQL Server インスタンスで実行するよう構成してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースの処理を要するアプリケーション、その分離、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと格納される SQL Server コンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースがパフォーマンスが向上し、実稼働でのベスト プラクティスを考慮する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境.  
  
 さまざまなエディション[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]のパフォーマンスが低下する可能性がさまざまな機能を提供、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 など、高負荷条件下で使用可能な数のデータベースの 32 ビット バージョンで利用可能なロック[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を超える可能性が、これは、BizTalk ソリューションのパフォーマンスを低下させます。 テスト環境でロックの範囲外"エラーが発生した場合、64 ビット バージョンの SQL Server にメッセージ ボックス データベースを格納していることを検討してください。 64 ビット バージョンの SQL Server では、使用できるロックの数が大幅に増えます。  
  
 BizTalk 環境に必要な機能するとき、データベース エンジンの決定を下にあるテーブルを検討してください。 例を実行しているときに、小規模なソリューションを[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Branch エディション[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Workgroup Edition ハウジングに適合している可能性があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 大規模なエンタープライズ レベルのソリューションをクラスタ リングを必要とするサポート、BizTalk ログ配布のサポート、または Analysis Services がサポートして必要があります[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]ハウスに Enterprise Edition、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。  
  
|SQL Server のバージョンとエディション|64 ビットのサポート|複数インスタンスのサポート|クラスタ リングのサポート|Analysis Services|  
|---------------------------------------|---------------------|-----------------------------|------------------------|-----------------------|  
|SQL Server 2008 SP1 または SQL Server 2008 R2 Enterprise Edition|はい|可|可|はい|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] / [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Standard Edition|はい|はい|[はい] (2 ノード)|はい|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] / [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Workgroup Edition|はい|可|いいえ|不可|  
  
> [!NOTE]  
>  BAM RTA 必要[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Enterprise Edition。  
  
 各エディションでサポートされる機能の完全な一覧については[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]を参照してください[、エディションの SQL Server 2008 R2 でサポートされる機能](http://go.microsoft.com/fwlink/?LinkId=151940)([http://go.microsoft.com/fwlink/?LinkId = 151940](http://go.microsoft.com/fwlink/?LinkId=151940)) で、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]ドキュメント。