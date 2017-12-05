---
title: "高可用性と、Microsoft Operations Framework |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- high availability, managing
- service management functions (SMFs)
- service continuity management
- jobs, scheduling
- MOF, high availability
- change management
- MOF, process model
- high availability, MOF
ms.assetid: 54d8bae3-b241-4371-b8fc-a9cbdca6b495
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8361875cf34f14118fb93818c78a6ca7d12a86f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="high-availability-and-the-microsoft-operations-framework"></a>高可用性と MOF
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に対する高可用性ソリューションを計画および実装する際、MOF (Microsoft Operations Framework) プロセス モデルを適用することにより、リリース ライフ サイクルのさまざまな段階で適切なプロセスを得ることができます。 高可用性に影響するすべてのライフ サイクル ステージをあらかじめ把握しておくことにより、可用性の問題に伴うインストール、メンテナンス、およびトラブルシューティングを、より円滑に行うことができます。  
  
 このセクションでは、高可用性を実現するために必要な MOF プロセスについて考えていきます。  
  
## <a name="microsoft-operations-framework-process-model"></a>MOF プロセス モデル  
 MOF (Microsoft Operations Framework) とは、Microsoft の製品とテクノロジに基づいたミッション クリティカルなシステムの信頼性、可用性、保守性、および管理容易性を実現するための指針です。 運用上の指針は、ホワイト ペーパー、運用ガイド、評価ツール、ベスト プラクティス、ケース スタディ、テンプレート、サポート ツール、およびサービスの形態で提供されます。 これにより、分散された複雑な異種混合 IT 環境に伴う、要員、プロセス、技術、および管理の問題の解決を図ります。 Microsoft Operations Framework の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=31988](http://go.microsoft.com/fwlink/?LinkId=31988)です。  
  
 企業にとって、MOF プロセス モデルには次のような利点があります。  
  
-   サービス ソリューション全体にわたり、一貫した IT サービス管理を円滑に行うことができる。  
  
-   IT の機能、プロセス、および手順を体系的に捉えることができる。  
  
-   ライフサイクル ベースのアプローチが可能になる。  
  
 MOF プロセス モデルの大きな特徴は、SMF (Service Management Function) と呼ばれる運用プロセスおよび手順を 4 つの領域に分けることです。 SMF は、IT 環境の運用と保守の基礎となるベスト プラクティスと規範的な指針です。  
  
 次の図は、高可用性を実現する上で考慮する必要のある MOF プロセスを示しています。  
  
 ![MOF プロセス](../core/media/tdi-highava-mof.gif "TDI_HighAva_MOF")  
  
## <a name="changing-quadrant"></a>変更領域  
 変更領域には、管理対象となる IT 環境への変更を見極め、レビューし、さらに、それを承認して実行に移す、というプロセスに必要な SMF (Service Management Function) が含まれます。 ソフトウェア、ハードウェア、ドキュメント、役割/責任の変更のほか、特定のプロセスや手順に対する変更も含まれます。  
  
### <a name="change-management"></a>変更管理  
 変更管理は、テクノロジ、システム、アプリケーション、ハードウェア、ツール、ドキュメント、プロセスなどにおける変更のほか、役割や責任の変更をつかさどるプロセスです。  
  
 BizTalk Server 導入計画の一部として、変更管理プロセスでは次のような作業が考えられます。  
  
-   パートナーまたは顧客とのサービス レベル契約に、一定水準の可用性、アップタイム、負荷処理の機能を約束する項目があるかどうかを確認します。  
  
-   アップグレードする場合は[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]または[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]BizTalk Server に BizTalk Server の最小ハードウェア要件とサービス レベル契約から要件に、既存のハードウェアが満たしているかどうかを判断する必要があります。  
  
-   ビジネス ニーズに合わせて、BizTalk Server データベースの最適なクラスター構成を確認します。 実行時の環境では、BizTalk 管理データベース、メッセージ ボックス データベース、追跡分析サービス データベース、BAM 分析データベース、BAM スター スキーマ データベース、BAM プライマリ インポート データベース、および BAM アーカイブ データベースへの書き込み処理が行われます。 したがって、これらのデータベースを障害から保護することが特に重要となります。当然、どのデータベースをクラスター化するかという判断において、より高い優先順位が付けられることになります。 その他のデータベースに対する書き込みは、ユーザーまたはツールによってのみ行われます。 メッセージ ボックス データベースについては、4 つのサーバー クラスターから成るアクティブ/アクティブ/アクティブ/パッシブ構成によって、必要なハードウェアを最小限に抑えることができます。  
  
-   マスター シークレット サーバーをクラスター化すべきかどうかを決めます。あるいは、マスター シークレットを別のエンタープライズ シングル サインオン サーバーに手動で復元するだけで十分かもしれません。 ただしこのソリューションで提供できるのは可用性であり、高可用性ではありません。  
  
-   推定されるメッセージ量を適切に処理し、高可用性の要件を満たすために必要なホスト数およびホスト インスタンス数を確認します。  
  
-   変更管理プロセスにかかわる要員のリストを作成します。 このリストには、ドメイン管理者、データベース管理者、インフラストラクチャ管理者、BizTalk Server 管理者、IT 運用スタッフなどが含まれます。  
  
### <a name="configuration-management"></a>構成管理  
 構成管理は、ソフトウェア、ハードウェア、ドキュメント、プロセス、手順など、変更管理プロセス下にある IT 環境のあらゆる構成要素のバージョンをすべて識別、管理、追跡するプロセスです。  
  
 構成管理プロセスでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性ソリューションを具体的にどのように実現するかという詳細な計画を立てる必要があります。 ソリューションの作成に要した手順を記録しておくことも必要です。 大まかな手順としては、次のようなことが含まれます。  
  
-   ドメイン コントローラーで、BizTalk Server 環境で使用するドメイン グループおよびアカウントを作成する。  
  
-   インフラストラクチャ管理者が、BizTalk Server データベース用およびマスター シークレット サーバー用の Windows クラスターを作成する。  
  
-   データベース管理者が、BizTalk Server データベース用 Windows クラスターに、Microsoft SQL Server をインストールおよび構成する。  
  
-   BizTalk Server 管理者が、マスター シークレット サーバー クラスターを構成する。  
  
-   BizTalk Server 管理者が、処理サーバー、受信サーバー、および送信サーバーに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールおよび構成する。  
  
-   BizTalk Server 管理者が、適切なサーバー上にホストを作成し、ホスト インスタンスをインストールすることによって可用性や処理能力の向上を図る。  
  
## <a name="operating-quadrant"></a>運用領域  
 運用領域には、サービス ソリューションを毎日監視および管理するために必要な SMF が含まれています。これにより、定義済みパラメーター内のサービス レベルを確保、維持します。  
  
### <a name="job-scheduling"></a>ジョブ スケジューリング  
 ジョブ スケジューリングには、システムのスループットを最大限に引き出し、サービス レベル契約の要件を満たしながら、ジョブとプロセスの最も効率のよい流れを体系化する作業が含まれます。  
  
 更新プログラムなどのメンテナンス ダウンタイムをスケジューリングする場合は、業務への影響をできるだけ小さくするために、メッセージ処理の負荷が低い時間帯を選ぶようにしてください (夜中など)。  
  
## <a name="supporting-quadrant"></a>サポート領域  
 サポート領域には、インシデントや問題、リクエストなどを、サービス レベル契約の要件を満たす範囲内で処理 (識別、割り当て、診断、追跡、解決) するために必要な SMF が含まれます。  
  
## <a name="optimizing-quadrant"></a>最適化領域  
 最適化領域には、サービス レベルを維持または向上させながら IT コストを削減することによって、企業や IT 部門の運営に貢献する SMF が含まれます。 たとえば、障害やインシデントの再検証、コスト体系やスタッフ割り当ての見直し、可用性やパフォーマンスの分析、処理能力予測などがあります。  
  
### <a name="service-level-management"></a>サービス レベル管理  
 サービス レベル管理の目的は、サービス レベルの要件を絶えず調整および監視しながら、IT サービスの品質を維持し、持続的に向上させることです。 サービス レベル管理がうまく機能すれば、サービス品質の改善や、顧客の生産性向上といった効果が期待できます。サービスにかかる総コストまで削減できれば理想的です。  
  
 サービス レベル管理プロセスには、次のような作業が含まれます。  
  
-   現在の環境がサービス レベル契約の要件を満たしているかを実際的な観点から評価します。  
  
-   要件を満たすためにメッセージの処理、受信、または送信用の新しいサーバーを追加する必要があれば、それを提案します。  
  
-   サービス レベル契約の可用性要件を満たすだけの耐性のない、障害の発生しやすい箇所に対し、必要に応じて高可用性ソリューションの適用を提案します。  
  
### <a name="availability-management"></a>可用性管理  
 可用性管理の目的は、顧客が特定の IT サービスを、必要なときにいつでも利用できるようにするという一点につきます。  
  
 可用性管理プロセスでは、たとえば、サーバーの負荷が特定のしきい値を上回った場合や、ハードウェア障害が発生し、早急に修理または交換が必要となった場合に、そのことを速やかに IT 担当者に通知するためのメカニズムを構築することなどが考えられます。  
  
### <a name="service-continuity-management"></a>サービス継続性管理  
 サービス継続性管理機能の目的は、標準の可用性ソリューションでは対応できないような問題が発生したとしても、特定の IT サービスが顧客に価値を提供できるようにすることです。  
  
 サービス継続性機能の中に、お客様にも計画または計画外のダウンタイムが発生すると、期待されるサービスを提供し続けることを確認するために実装するには、どのような高可用性構成を確認する必要があります。 計画外のダウンタイムには、ハードウェア障害や自然災害などがあります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の高可用性を実現するサンプル シナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)