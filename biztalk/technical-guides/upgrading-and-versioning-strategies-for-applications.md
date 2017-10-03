---
title: "アップグレードとアプリケーションのバージョン管理方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6763cb76cb0471d56a31e88ff95acea439bff077
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a>アップグレードとアプリケーションのバージョン管理方法
BizTalk ソリューション サイド バイ サイド、2 つのバージョンを実行する必要がある場合、または新しいバージョンを展開する BizTalk アプリケーションのダウンタイムを使用できない場合、BizTalk アプリケーションのバージョン管理は問題になることができます。 同時に (たとえば、あるありません長時間のオーケストレーション)、ソリューションの 2 つのバージョンを実行する必要はありません、サービスのメンテナンス期間使用できない場合、完全に再現してもかまいません。 以前のバージョンを展開解除し、新しいバージョンをデプロイし、バージョン管理戦略 (アセンブリのバージョン管理なし) として これが可能なバージョン管理の戦略では、まだファイル バージョン番号のインクリメントをお勧め (バージョンが実行しているコンピューターに展開されていることを確認できますを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
## <a name="when-to-use-versioning"></a>バージョン管理を使用する場合  
 かどうかは、長時間のオーケストレーションをサポートする必要があります、または BizTalk アプリケーションのダウンタイムなしでの BizTalk アプリケーション展開を実行する必要があります、信頼性の高いエンド ツー エンドのプラクティスを実装する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のバージョン管理の戦略、異なるバージョン管理のシナリオです。 これは、.NET アセンブリのバージョン管理スキーマ、マップ、パイプライン、パイプライン コンポーネント、オーケストレーション、カスタム アダプターを含む、すべての BizTalk アイテムのバージョン管理、およびカスタム クラスで呼び出されたオーケストレーションとマップ、ビジネス ルール、および BAM です。  
  
 スキーマのバージョン管理されている内で一意で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプラインによって決定されます、ターゲットの名前空間とルート ノードに基づくメッセージのメッセージの種類、スキーマで定義された名前です。 詳細については、次を参照してください。[スキーマの解決パイプライン コンポーネントで](http://go.microsoft.com/fwlink/?LinkId=154207)(http://go.microsoft.com/fwlink/?LinkId=154207)。 スキーマをバージョンにする場合、バージョン インジケーターは、ターゲットの名前空間の一部をする必要があります。 スキーマのバージョンの変更、ソリューション全体に影響がありそのため、事前に計画する必要があります。 MSDN マガジンの記事の推奨事項に従って、オーケストレーションのメッセージを作成するときに[BizTalk サーバー: 向上 BizTalk プログラミングの 8 ヒントとテクニック](http://go.microsoft.com/fwlink/?LinkId=101594)、ヒント 1:「常に使用してマルチパート メッセージの種類」(http://go.microsoft.com/fwlink/ しますか。LinkId = 101594)。 このメソッドを使用する柔軟性の向上とスキーマのバージョン管理します。  
  
## <a name="using-factoring-for-assembly-versioning"></a>アセンブリのバージョン管理のファクタリングを使用します。  
 長時間のオーケストレーション、サイド バイ サイド展開やダウンタイムのないアップグレードをサポートする必要がある場合は、アセンブリのバージョン管理とパッケージ化戦略を実装する必要があります。 BizTalk アイテムのアセンブリのバージョン管理を実行するために、BizTalk ソリューションのアセンブリ必要がある考慮する (パッケージ) を許可するように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョン管理します。  リファクタリングに関する次の 3 つの種類があります。  
  
-   **ありませんファクタリング**  
  
     すべての BizTalk アイテムは、1 つのアセンブリでです。 これは、最も理解および展開するが最低限の柔軟性を提供します。  
  
-   **完全ファクタリング**  
  
     各 BizTalk 成果物は、独自のアセンブリでです。 これは、最大限の柔軟性を提供が複雑では、最もを展開し、理解します。  
  
-   **最適なファクタリング**  
  
     どこかに中間「ファクタリングなし」と「完全ファクタリング」は、BizTalk アプリケーションの詳細な分析に基づいています。 バージョン管理、に加えてこれにより、BizTalk ホストの設計を簡単に実装できます。 これは、BizTalk アイテム間の関係を探すことにより実現されます。 常には、バージョンが一緒にいる成果物は、同じアセンブリに通常配置できます。 成果物の独立したバージョンが必要な場合は、異なるアセンブリに配置する必要があります。 これは、レベルを実現したいのファクタリングします。  
  
## <a name="additional-resources"></a>その他のリソース  
 実装とチューニングのベスト プラクティスの詳細については、次を参照してください。 [MSDN web キャスト: 導入および BizTalk Server ソリューションのチューニングのベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=101595)(http://go.microsoft.com/fwlink/?LinkId=101595)。  
  
 定義し、練習をする必要がありますのサイド バイ サイドの配置方法を提供することを確認する方法を純色のバージョン管理します。 BizTalk Server アプリケーションのアップグレードおよびバージョン管理の戦略のリソースを以下に示します。  
  
-   [アプリケーションの更新](../technical-guides/updating-an-application.md)  
  
-   [BizTalk アプリケーションの更新](http://go.microsoft.com/fwlink/?LinkId=154208)(http://go.microsoft.com/fwlink/?LinkId=154208) およびサブトピックです。  
  
-   [BizTalk Server プロジェクトのバージョン管理](http://go.microsoft.com/fwlink/?LinkId=154209)(http://go.microsoft.com/fwlink/?LinkId=154209)  
  
-   [BizTalk Server アプリケーションの展開を理解する](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)  
  
-   [BizTalk Server 2006 - パイプライン コンポーネント サイド バイ サイド展開](http://go.microsoft.com/fwlink/?LinkId=101600)(http://go.microsoft.com/fwlink/?LinkId=101600)  
  
-   [説明と短いビデオ デモを BizTalk Server 2006 のライフ サイクル](http://go.microsoft.com/fwlink/?LinkId=101601)(http://go.microsoft.com/fwlink/?LinkId=101601)  
  
> [!NOTE]  
>  これらの記事の一部が専用に作成された場合でも[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]、そのコンテンツにも適用されます[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]です。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server を構成します。](../technical-guides/checklist-configuring-biztalk-server.md)