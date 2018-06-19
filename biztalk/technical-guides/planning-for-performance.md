---
title: パフォーマンスの計画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267a8bc6-a0ab-4335-bc04-c22d5a56792f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fac21f0b483ac3cbaec64c48b524a17422cb146
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22303002"
---
# <a name="planning-for-performance"></a>パフォーマンスの計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームです。 またはではないだけサーバー製品開発者製品だけです。 指向アーキテクチャのサービスを有効にして、ワークフロー、自動化する、エンタープライズ アプリケーション統合をビジネス プロセス管理システムを構築するために使用されるアプリケーション プラットフォームです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他の多くのソフトウェア コンポーネントに依存します。 BizTalk アプリケーション プラットフォームが通常以下のソフトウェア コンポーネントのいくつかを含む: Windows Server オペレーティング システム、SQL Server [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、IIS (省略可能)、外部システムを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]との対話はだけでなくMicrosoft 以外のアダプターとコンポーネント。  
  
 本質的に複雑な性質があるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、パフォーマンスの計画したときに多くの注意事項があります。 すべてに適用されるいくつかの既定の設定がある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境がある追加の考慮事項および最適化するための方法論特定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。  
  
 このトピックは、すべてのパフォーマンスを最適化する際に適用する既定の設定の概要を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 テストと最適化の推奨事項も用意されています[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定のシナリオ用に設計されている環境です。  
  
## <a name="settings-that-you-should-apply-to-all-biztalk-server-environments"></a>すべての BizTalk Server 環境に適用する設定  
 [運用の準備のチェックリスト](../technical-guides/operational-readiness-checklists.md)このガイドのセクションには、任意の BizTalk ソリューションを採用する前に確認する必要があります項目の一覧が含まれています。 このチェックリストにはパフォーマンスに大きな影響を持つことができるアクション項目が含まれています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]導入されている BizTalk ソリューションの特定の種類に関係なく環境。  
  
## <a name="considerations-for-testing-and-optimizing-a-biztalk-solution"></a>テストと、BizTalk ソリューションの最適化に関する考慮事項  
 別の BizTalk ソリューションでは、大幅にさまざまなパフォーマンス基準があります。 たとえば、BizTalk ソリューションが構築されています。 オーケストレーションの実行は、受信、変換、およびフラット ファイル ドキュメントのマッピングに特化した BizTalk ソリューションよりも、さまざまなパフォーマンス プロファイルがあります。 オーケストレーションに重点を置いたソリューションは、CPU の処理を要する場合があります。 またはフラット ファイル変換とマッピングに重点を置いたソリューションは、メモリの消費が多い、最適化の恩恵をカスタム コンポーネントを呼び出すことがあります。  
  
 アダプターとのドキュメントを送受信するために使用するパイプライン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk ソリューションのパフォーマンスに重大な影響を受けることもできます。 ソリューションに必要なドキュメントの追跡のレベルも大幅にパフォーマンスに影響します。 別の BizTalk ソリューションで使用できる多くの異なるパフォーマンス プロファイル、ためは非常に重要維持可能な最大のパフォーマンス、維持可能な最大の追跡のパフォーマンスを測定する BizTalk ソリューションをテストすることです。  
  
 維持可能な最大のパフォーマンスと、BizTalk ソリューションの維持可能な最大の追跡のパフォーマンスを決定した後、BizTalk ソリューションでボトルネックを解消するための特定の手順があります。 詳細については、次を参照してください。、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)