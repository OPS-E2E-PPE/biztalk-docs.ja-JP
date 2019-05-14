---
title: 運用準備チェックリスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b304b843806ed5550dd623d9980794a141083432
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400761"
---
# <a name="operational-readiness-checklists"></a>運用準備チェックリスト
運用準備チェックリストには、考慮すべき推奨事項とタスクを運用環境に BizTalk ソリューションをデプロイする前に実行する必要がありますが含まれています。 これらのチェックリストには、可用性の向上、前提条件のソフトウェアを構成するための情報が含まれます。 監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびテストする手順。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で依存関係が保持される他の多くの Microsoft テクノロジ、運用環境を確保しやすく依存している各テクノロジのタスクを完了する必要がありますので[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境をスムーズに実行します。  
  
## <a name="typical-prerequisite-software"></a>一般的な前提条件ソフトウェア  
 前提条件のソフトウェア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームには通常、次の製品が含まれています。  
  
- Windows オペレーティング システム  
  
- SQL Server 
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- Visual Studio (用に開発、実行時ではなく)  
  
## <a name="additional-components"></a>その他のコンポーネント  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームでは、次のソフトウェア コンポーネントのいくつか必要がありますも。  
  
- インターネット インフォメーション サービス (IIS)  
  
- SharePoint
  
- Microsoft Office Excel 
  
  > [!NOTE]  
  >  BizTalk Server には、Microsoft Office の 32 ビット バージョンのみがサポートしています。  
  
- SQL Server
  
- SQLXML 
  
- .NET Framework 
  
- 特定の機能を有効にする Microsoft 以外のコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。  
  
  さまざまな Windows オペレーティング システムのバージョンの BizTalk アプリケーション プラットフォームの特定の機能に必要な依存関係のソフトウェアの詳細については、次を参照してください[新機能、インストール、構成、アップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).
- 
  
## <a name="next-steps"></a>次のステップ
  
-   [チェックリスト:BizTalk Server の概要](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [チェックリスト:Windows Server を構成します。](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [チェックリスト:インターネット インフォメーション サービスを構成します。](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [チェックリスト:SQL Server の構成](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [チェックリスト:BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [チェックリスト:フォールト トレランスまたは負荷分散と高可用性を実現します。](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [チェックリスト:ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [チェックリスト:運用準備状況の監視](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [チェックリスト:メンテナンスと BizTalk Server データベースのトラブルシューティング](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [チェックリスト:運用準備のテスト](../technical-guides/checklist-testing-operational-readiness.md)