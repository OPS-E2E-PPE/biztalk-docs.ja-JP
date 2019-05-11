---
title: アップグレードと、アプリケーションのバージョンの戦略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdf9484d04ff895af42a3321d7ff44651c9bb26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261325"
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a>アップグレードして、アプリケーションのバージョン管理戦略
BizTalk ソリューション サイド バイ サイド、2 つのバージョンを実行する必要がある場合、または新しいバージョンを展開する BizTalk アプリケーションのダウンタイムを使用できない場合、BizTalk アプリケーションのバージョン管理は問題になることができます。 同時に (たとえば、あるありません実行時間の長いオーケストレーション)、ソリューションの 2 つのバージョンを実行する必要はありません、サービスのメンテナンス ウィンドウが使用できない場合は、古いバージョンの展開を解除して、新しいバージョンをデプロイするまったくバージョン管理戦略 (アセンブリのバージョン管理なし) として これは、まだファイルのバージョン番号をインクリメントをお勧めの可能なバージョン管理戦略では、(どのようなバージョンが実行しているコンピューターに展開されていることを知らせる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
## <a name="when-to-use-versioning"></a>バージョン管理を使用する場合  
 長時間のオーケストレーションをサポートする必要があるかどうかや BizTalk アプリケーションのダウンタイムなしでの BizTalk アプリケーション展開を実行する必要があり、信頼性の高い、エンド ツー エンドのプラクティスを実装する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のバージョン管理戦略、異なるバージョン管理のシナリオ。 カスタム クラスで呼び出されたオーケストレーションとマップ、ビジネス ルール、および BAM、これは、.NET アセンブリのバージョン管理、スキーマ、マップ、パイプライン、パイプライン コンポーネント、オーケストレーション、カスタム アダプターを含むすべての BizTalk アイテムのバージョン管理が含まれます。  
  
 スキーマのバージョン管理されている内で一意で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ターゲット名前空間とルート ノードに基づくメッセージのメッセージの種類を決定するパイプライン、スキーマで定義された名前。 詳細については、次を参照してください。[スキーマの解決パイプライン コンポーネントで](../core/schema-resolution-in-pipeline-components.md)します。 スキーマをバージョンにする場合のバージョンのインジケーターはターゲット名前空間の一部である必要があります。 スキーマのバージョンを変更して、ソリューション全体に影響が、そのため、事前に計画する必要があります。 オーケストレーションのメッセージを作成するときに検索**BizTalk サーバー。8 つのヒントとテクニック プログラミングを向上させる BizTalk** (ヒント 1。常に使用してマルチパート メッセージの種類)。 このメソッドを使用して柔軟性の向上とスキーマのバージョン管理します。  
  
## <a name="using-factoring-for-assembly-versioning"></a>アセンブリのバージョン管理のファクタリングを使用してください。  
 実行時間の長いオーケストレーション、サイド バイ サイドでのデプロイや、ダウンタイムのないアップグレードをサポートする必要がある場合は、アセンブリのバージョン管理とパッケージ化戦略を実装する必要があります。 BizTalk アイテムのアセンブリのバージョン管理を実行するために BizTalk ソリューションのアセンブリ必要がある考慮するを許可するように (パッケージ)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョン管理します。  ファクタリングの 3 つの種類があります。  
  
-   **なしのファクタリング**  
  
     すべての BizTalk アイテムは、1 つのアセンブリには。 これは、最も理解し、デプロイしますが、最小限の柔軟性を提供します。  
  
-   **完全なファクタリング**  
  
     各 BizTalk アイテムが、独自のアセンブリです。 これにより、最高の柔軟性を提供しますが、最も複雑なデプロイを理解するには。  
  
-   **最適なファクタリング**  
  
     どこかに間に「ファクタリングありません」と「完全なファクタリング」は、BizTalk アプリケーションの詳細な分析に基づいています。 バージョン管理、だけでなくこれにより、BizTalk ホストの設計を簡単に実装することです。 これは、BizTalk アイテム間の関係を探すことによって実現されます。 成果物をまとめてバージョン管理では常には、同じアセンブリを通常格納できます。 成果物の独立したバージョン管理が必要な場合は、異なるアセンブリに配置する必要があります。 これは、レベルを実現するを取り除いたものです。  
  
## <a name="additional-resources"></a>その他のリソース  
  
 定義し、確認する必要がありますのサイド バイ サイドで配置方法を提供する solid のバージョン管理戦略を実践します。 BizTalk Server アプリケーションのアップグレードおよびバージョン管理戦略のリソースを以下に示します。  
  
-   [アプリケーションの更新](../technical-guides/updating-an-application.md)  
  
-   [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)
  
-   [BizTalk Server プロジェクトのバージョン管理](../core/biztalk-server-project-versioning.md)  
  
-   [BizTalk Server アプリケーションの展開を理解します。](../core/understanding-biztalk-application-deployment-and-management.md)


  
## <a name="see-also"></a>参照  
 [チェックリスト:BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)
