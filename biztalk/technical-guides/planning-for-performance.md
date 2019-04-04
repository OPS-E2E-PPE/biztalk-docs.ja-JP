---
title: パフォーマンスの計画 |Microsoft Docs
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
ms.openlocfilehash: 452dd1a8a038ab151b98aac8ce6c4f93641f7361
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752714"
---
# <a name="planning-for-performance"></a>パフォーマンスの計画
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション プラットフォームです。 できませんサーバー製品や単なる開発者製品だけです。 これは、ワークフローを自動化する、エンタープライズ アプリケーションを統合する、ビジネス プロセス管理システムを構築するために使用するアプリケーション プラットフォームおよび指向アーキテクチャのサービスを有効にします。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 他の多くのソフトウェア コンポーネントに依存します。 以下のソフトウェア コンポーネントのいくつかは、BizTalk アプリケーション プラットフォームが通常に: Windows Server オペレーティング システム、SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、IIS (省略可能)、外部システムを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が使用すると、対話だけでなくMicrosoft 以外のアダプターとコンポーネント。  
  
 本質的に複雑な性質のため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、パフォーマンスの計画時に多くの考慮事項があります。 すべてに適用されるいくつかの既定の設定は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境固有は追加の考慮事項とを最適化するための方法論と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。  
  
 このトピックでは、すべてのパフォーマンスを最適化する際に適用する既定の設定の概要を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 テストと最適化の推奨事項も提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定のシナリオ用に設計された環境。  
  
## <a name="settings-that-you-should-apply-to-all-biztalk-server-environments"></a>すべての BizTalk Server 環境に適用する設定  
 [運用準備チェックリスト](../technical-guides/operational-readiness-checklists.md)このガイドのセクションには、BizTalk ソリューションを採用する前に確認する必要があります項目の一覧が含まれています。 このチェックリストにはパフォーマンスに大きな影響を与えることができますアクション項目が含まれています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]導入されている BizTalk ソリューションの特定の性質にかかわらず環境。  
  
## <a name="considerations-for-testing-and-optimizing-a-biztalk-solution"></a>テストと、BizTalk ソリューションの最適化に関する考慮事項  
 さまざまな BizTalk ソリューションでは、大幅に異なるパフォーマンス基準があります。 たとえば、受信、変換、およびフラット ファイル ドキュメントのマッピングに重点を置いていますが、BizTalk ソリューションをよりさまざまなパフォーマンス プロファイル オーケストレーションの実行を中心として構築する BizTalk ソリューションになります。 オーケストレーションに重点を置いたのソリューションでは、CPU の処理を要する場合があります。 または最適化、メリットをフラット ファイル変換およびマッピングに重点を置いたソリューションがよりメモリを消費するカスタム コンポーネントを呼び出すことができます。  
  
 アダプターとのドキュメントを送受信するために使用するパイプライン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk ソリューションのパフォーマンスに大きな影響をこともできます。 ソリューションに必要なドキュメントの追跡のレベルも大幅にパフォーマンスに影響します。 さまざまな BizTalk ソリューションで可能な多くの異なるパフォーマンス プロファイル、ためには、維持可能な最大のパフォーマンスと最大持続可能な追跡のパフォーマンスを測定する BizTalk ソリューションをテストすることがきわめて重要が。  
  
 維持可能な最大のパフォーマンスと、BizTalk ソリューションのパフォーマンスを維持できる最大の追跡を決定した後、BizTalk ソリューションでボトルネックを解消する特定の手順があります。 詳細については、、 [BizTalk Server 2009 パフォーマンス ガイド](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)を参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)