---
title: "運用の準備のチェックリスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87da295129a4cb90ecf643cd06eb18ac3e6aa18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operational-readiness-checklists"></a>運用の準備のチェックリスト
運用の準備のチェックリストには、考慮すべき推奨事項と、BizTalk ソリューションを実稼働環境に展開する前に行う必要がありますタスクが含まれています。 これらのチェックリストには、前提条件ソフトウェアの可用性を高める構成に関する情報が含まれます。 監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびテストする手順。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で依存関係が維持される他の多くの Microsoft テクノロジとなるように、実稼働環境に依存している各テクノロジのタスクを完了する必要がありますので[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境がスムーズに実行されます。  
  
## <a name="typical-prerequisite-software"></a>一般的な前提条件ソフトウェア  
 前提条件ソフトウェア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームには通常、次の製品が含まれています。  
  
-   Windows オペレーティング システム  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]SP1 または[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)](開発目的の実行時ではなく)  
  
## <a name="additional-components"></a>その他のコンポーネント  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームもかかる場合、次のソフトウェア コンポーネントのいくつか。  
  
-   インターネット インフォメーション サービス (IIS)  
  
-   Windows SharePoint® Services 2010  
  
-   SharePoint Foundation 2010  
  
-   Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)  
  
-   SP1 または SP2、Windows SharePoint Services 3.0  
  
-   Microsoft Office Excel 2010 または 2007  
  
    > [!NOTE]  
    >  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Microsoft Office 2010 の 32 ビット バージョンのみをサポートしています。  
  
-   SQL Server 2005 Notification Services  
  
-   SQLXML 4.0 Service Pack 1  
  
-   .NET framework 1.0  
  
-   .NET Framework 2.0  
  
-   .NET framework 3.0  
  
-   Microsoft .NET Framework 4 および .Net Framework 3.5 Service Pack 1 (SP1)  
  
-   特定の機能を有効にする Microsoft 以外のコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。  
  
 さまざまな Windows オペレーティング システムのバージョンの BizTalk アプリケーション プラットフォームの特定の機能に必要な依存関係ソフトウェアに関する詳細についてを参照してください「機能の依存関係の一覧」で、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]インストールし、特定の Windows オペレーティング システムのバージョンのガイドをアップグレードします。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]インストールおよびアップグレード ガイドはいただけます[http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チェックリスト: BizTalk Server の概要](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [チェックリスト: Windows Server を構成します。](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [チェックリスト: インターネット インフォメーション サービスを構成します。](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [チェックリスト: SQL Server を構成します。](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [チェックリスト: BizTalk Server を構成します。](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [チェックリスト: フォールト トレランスと負荷分散と高可用性を実現します。](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [チェックリスト: 災害復旧と可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [チェックリスト: 監視の運用の準備](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [チェックリスト: を維持し、BizTalk Server データベースのトラブルシューティング](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [チェックリスト: テスト運用の準備](../technical-guides/checklist-testing-operational-readiness.md)