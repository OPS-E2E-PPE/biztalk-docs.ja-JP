---
title: "BizTalk ESB Toolkit の概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9763e55c44fc3ea45ab93127ffae8c9c742f0dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a>BizTalk ESB Toolkit の概要
アーキテクチャと Microsoft の内容について説明します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 サービスを有効にする柔軟なセキュリティで保護された、エンタープライズ アプリケーションを開発する Enterprise Service Bus (ESB) アーキテクチャ パターンを適用する方法および再利用可能なサービスと新しいエンド ツー エンドに既存のサービスの迅速な組織にも、ドキュメントを示していますビジネス プロセス。  
  
## <a name="what-is-an-enterprise-service-bus"></a>Enterprise Service Bus とは何ですか。  
 Enterprise Service Bus は、サービス指向アーキテクチャ (SOA) を有効にするためのインフラストラクチャの実装のコンテキストで広く使用する用語。 ただし、SOA ソリューションの配置を使用して実際の動作では、こと、ESB は包括的なサービス指向インフラストラクチャ (SOI) をビルドに必要な多くのコンポーネントの 1 つだけが示されています。 さまざまな方向で進化してきました"ESB"という用語は、— 個々 の ESB ベンダーおよび統合プラットフォーム ベンダーの解釈とは、特定の SOA イニシアティブの要件とその定義が異なります。  
  
 Microsoft が成功した多くの現実世界 SOI 実装から収集した経験に基づき、Microsoft が判断 Enterprise Service Bus で従来エンタープライズ アプリケーション統合 (EAI)、ベース アーキテクチャのパターンのコレクションであることメッセージ指向ミドルウェア、Web サービス、.NET と Java の相互運用性、ホスト システム統合、およびサービス レジストリおよび資産リポジトリとの相互運用。 図 1 は、エンタープライズ サービス バスのアーキテクチャを示しています。  
  
 ![ESB の概要](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **図 1**  
  
 **Enterprise Service Bus アーキテクチャで提供される接続の概要を示したもの**  

\<!---古いリンクを含む古いテキスト
## <a name="the-industry-view-of-esb"></a>ESB の業界ビュー  
 ESB デザイン、アーキテクチャ、インフラストラクチャ、および実装に関する情報の多くのソースが業界サプライヤー、システム インテグレーターと独立したソースから入手できます。  
-->
\<!---    
 IBM システムとしての ESB の定義を".. .enables 包括的な柔軟なのでを使用して、一貫した方法でも統合されているアプリケーションの複雑さを削減しながら統合にするのには business です。 性質の複雑でさまざまなビジネス ニーズ、ESB はメッセージ指向を統一する evolutional 進行、イベント ドリブンおよびサービス指向アプリケーションとサービスを統合するための方法です。" IBM と利点を説明する".. の数、サイズ、および統合インターフェイスの複雑さを減らすことができますので、アプリケーション ロジックと統合タスクを分離することで IT 資産 .greater を再利用"と、権限を許可する".. 最小限に抑えて .add または変更のサービス既存の IT 環境の中断コストとビジネスの変化に伴うリスクを軽減し、新しいビジネス チャンスが発生する。" 詳細については、次を参照してください。 [WebSphere ソフトウェア](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))、IBM の Web サイトにします。  
-->
\<!---Sonic ソリューションに提供される、ESB の包括的な検査 IT 原則の側面について説明するリンクが以前に古いテキストとビジネスの利点があります。 ESB の要件について説明します"新旧を統合するサービス指向アーキテクチャ (SOA) 必要がありますが接続できる、IT リソース、どのようなインフラストラクチャのテクノロジまたは展開されている任意の場所。"。 詳細については、次を参照してください。 [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) Sonic ソリューションの Web サイトにします。  
-->
\<!---古いリンク TIBCO ソフトウェアと共に古いテキストを定義として ESB".. をするために複数の通信プロトコルに [] サービスの展開を簡略化するサービスを有効にするサービス指向アーキテクチャ (SOA) で .a 標準ベースの通信レイヤーと管理、異機種混在環境でサービスを再利用を昇格します"。 Esb、これらの機能を提供するため、提案、".. 共にオープン標準と Web サービスを検出して発行 UDDI ベース レジストリなど、独自のテクノロジー .support services、Java Message Service (JMS) およびその他の広く導入されています。メッセージング プロトコル、標準に準拠した (XML) 変換、および基本的なメッセージをルーティングします。" 詳細については、次を参照してください。 [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) TIBCO Web サイトです。  
-->
\<!---、著書 Enterprise Service Bus の説明にリンクが以前に古いテキスト作成者 David chappell 氏ことを示す"ではなくより従来のエンタープライズ アプリケーション統合製品のハブ アンド スポーク アーキテクチャに準拠して、ESB は、高分散方法の統合。" 追加".. 個々 の部門または事業単位を作成できるようにする過ぎた固有の機能が同時に接続する独自のローカル管理と、自律的なを維持する、増分、という事実のチャンクで、統合プロジェクトの出力ごと統合プロジェクトより大きいより多くのグローバル統合ファブリック、またはグリッドです。" 詳細については、David chappell 氏によって Enterprise Service Bus を参照してください。  
-->
\<!---古いリンクを含む古いテキスト
-   Chappell、David です。 Enterprise Service Bus。 ◆、CA: o ' reilly のメディア, inc.2004.  
-->

  
## <a name="the-biztalk-esb-toolkit"></a>BizTalk ESB Toolkit
 このドキュメントでは、全体として設計者と開発者に導入 ESB アーキテクチャ概念によってアドレス指定されると、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、一般に受け入れられた ESB ユース ケースのセットを ESB コンポーネントの機能について説明します。  
  
 このセクションで説明の概要については、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、次のトピックが含まれています。  
  
-   [BizTalk ESB Toolkit の概要](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [BizTalk ESB Toolkit の内容](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 このドキュメントには、次のトピックのセクションも含まれます。  
  
-   [BizTalk ESB Toolkit の概要](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [主要なシナリオおよび開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [Itinerary Designer を使用して日程を作成します。](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [BizTalk ESB Toolkit のサンプル アプリケーション](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [変更して、BizTalk ESB Toolkit の拡張](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [BizTalk ESB Toolkit を使用した管理](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [SOA ガバナンスの統合](../esb-toolkit/soa-governance-integration.md)  
  
-   [トラブルシューティング](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)