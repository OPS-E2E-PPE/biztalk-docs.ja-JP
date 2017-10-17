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
ms.openlocfilehash: f9e9297e5539fd95f316ebbf6239a5d017ec4ecf
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="operational-readiness-checklists"></a>運用の準備のチェックリスト
運用の準備のチェックリストには、考慮すべき推奨事項と、BizTalk ソリューションを実稼働環境に展開する前に行う必要がありますタスクが含まれています。 これらのチェックリストには、前提条件ソフトウェアの可用性を高める構成に関する情報が含まれます。 監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびテストする手順。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で依存関係が維持される他の多くの Microsoft テクノロジとなるように、実稼働環境に依存している各テクノロジのタスクを完了する必要がありますので[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境がスムーズに実行されます。  
  
## <a name="typical-prerequisite-software"></a>一般的な前提条件ソフトウェア  
 前提条件ソフトウェア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームには通常、次の製品が含まれています。  
  
-   Windows オペレーティング システム  
  
-   SQL Server 
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Visual Studio (開発目的で、実行時ではなく)  
  
## <a name="additional-components"></a>その他のコンポーネント  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームもかかる場合、次のソフトウェア コンポーネントのいくつか。  
  
-   インターネット インフォメーション サービス (IIS)  
  
-   SharePoint
  
-   Microsoft Office Excel 
  
    > [!NOTE]  
    >  BizTalk Server には、Microsoft Office の 32 ビット バージョンのみがサポートしています。  
  
-   SQL Server
  
-   SQLXML 
  
-   .NET Framework 
  
-   特定の機能を有効にする Microsoft 以外のコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。  
  
 さまざまな Windows オペレーティング システムのバージョンの BizTalk アプリケーション プラットフォームの特定の機能に必要な依存関係のソフトウェアの詳細については、次を参照してください[は新規、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。.
- 
  
## <a name="next-steps"></a>次の手順
  
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