---
title: SWIFTNet とは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b074385-352c-40f4-b73e-1891c627aa4e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a46f793f55d92d020c989569bcbc2d7e5a74c61b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364080"
---
# <a name="what-is-swiftnet"></a>SWIFTNet とは何ですか。
汎用の財務業界の業界標準のソリューションとしては、SWIFTNet はグローバル金融コミュニティに参加しているすべての教育機関のすべての接続されているアプリケーションへのアプリケーションに依存しない、1 つのウィンドウ インターフェイスを提供します。 各サービス管理者のビジネス ポリシーの決定によって、インフラストラクチャの技術的な制限ではなく、実際のアクセスが制御されます。  
  
 SWIFTNet は、民間企業の境界を越えるミッション クリティカルな財務アプリケーションのインフラストラクチャのビジネス継続性とディザスター リカバリーを確保するための基礎を提供します。 SWIFTNet は、ミッション クリティカルな財務ソフトウェア ソリューションの相互運用性の制度化されたコミュニティの要件を満たす設計されています。  
  
 相互接続されたビジネス アプリケーション、SWIFTNet には、以下が用意されています。  
  
-   インフラストラクチャの信頼性の保証  
  
-   可用性  
  
-   ロール ベースおよび役割に基づいたアクセス制御  
  
-   送信者とメッセージの認証  
  
-   メッセージの整合性  
  
-   機密性  
  
-   否認不可のサポート  
  
-   メッセージの検証  
  
-   ストア アンド フォワード  

SWIFTNet を使用して**SWIFTNet リンク**(SNL) SWIFTNet サービス、および使用のアプリケーション プログラミング インターフェイスとして、 **SWIFTAlliance ゲートウェイ**接続し、使いやすさ。 このトピックでこれらのリソースについてもっと読む。

## <a name="swiftnet-link-overview"></a>SWIFTNet リンクの概要

ビジネス ソフトウェア アプリケーションにアクセスして SWIFTNet サービスを使用する SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) を使用します。 SNL は SWIFTNet、必須のネットワーク インターフェイスです。 SWIFTNet では、すべての外部インターフェイスの SNL が必要です。 SNL には、メッセージング、セキュリティ、およびサービス管理機能をサポートするバック グラウンド プロセスも含まれています。 SNL は SWIFTAlliance WebStation と SWIFTAlliance ゲートウェイ (SAG) に組み込まれます。  
  
 SNL は、ビジネス アプリケーション コンポーネント間の疎結合のクライアント/サーバーの関係を確立します。 メソッドまたは関数を直接呼び出すのではなく、相互作用にはメッセージ指向: 構造化されたメッセージはクライアントとサーバー間で渡されます。 一般に SWIFTNet サービス用に設計されたビジネス アプリケーションは、クライアントとサーバーのセットで構成されます。 同じクライアントまたは同じサーバー プロセスに複数回を開始できます。 のどのプロセス インスタンスが同じアプリケーションの受信メッセージ要求の配信を予測することはできませんに注意してください。 クライアント プロセス内で複数のスレッドは、SwCall API 関数を呼び出すことができます。 サーバー プロセスは、複数のスレッドも; を持つことができます。ただし、1 つのスレッドは SwCallback を呼び出すことができます。 クライアントとサーバー プロセスは、同じプロセス内で組み合わせることはできません。  
  
 SNL は、一連の高可用性と高スループットの環境用に設計されたトランスポート レベルの機能を提供します。 これらの機能は次のとおりです。  
  
- 負荷分散  
  
- 場所の透過性とルーティング、基になるトランスポート テクノロジから、アプリケーション コンポーネントを保護できます。  
  
- トランスポート レベルの認証と機密性、SNL 内にパッケージ化し、アプリケーションに透過的に提供  
  
- セキュリティ関数のアプリケーション ソフトウェアはビジネスによってエンド ツー エンドのセキュリティ (ユーザー アプリケーションにユーザー アプリケーション) を確立することが必要です。  
  
  ソース コード レベルを使用してでのプログラミングの観点からC++だけ 2 つの関数は、Java または。SwCall SwCallback. SwCall は、SWIFTNet を通じてサーバー アプリケーションにアクセスするクライアント アプリケーションによって使用されます。 SwCallback は、SWIFTNet 経由のクライアントに応答するサーバー アプリケーションによって使用されます。  
  
  SwCall と SwCallback 関数は、構造化された XML メッセージとの間の SWIFTNet を渡すことによって SWIFTNet の機能にアクセスします。 SNL には実行時に、両方のソフトウェア ライブラリが含まれています: ビジネス アプリケーションのクライアントまたはサーバーのプロセスと同じアドレス空間内のコードを実行します-アドレス空間を独立したプロセス (デーモンまたはサービス) が自分で実行されるとします。 ソフトウェア ライブラリは、SNL Api を介してアクセスできます。  

## <a name="swiftalliance-gateway-overview"></a>SWIFTAlliance Gateway の概要
  
SWIFTAlliance ゲートウェイ (SAG) は、インターフェイスの SWIFTNet 製品です。 SWIFTNet リンクのすべての機能が組み込まれています。 さらに、提供いくつかの異なる接続と操作性機能 SWIFTNet ユーザーは、統合に関する問題のシステムのさまざまなソリューションを提供します。  
  
 SAG 操作のいくつかの異なるモードをサポートしています。 これらの厳密な SWIFTNet リンク モードの 1 つは、SWIFT の FileAct および InterAct アダプターに特に関連します。 SWIFTNet リンク厳格モードで、SAG は、メッセージングのインターフェイスは、これらのトピックで説明されている、SWIFTNet リンク インターフェイスと同等の機能を表示します。  
  
 SAG は、メッセージ コンセントレーターとして機能します。 さまざまな他のアプリケーションからメッセージを受信しに SWIFTNet を通過します。 により、ビジネス アプリケーション SWIFTNet を経由してメッセージを渡すには、さまざまな異なる種類のコンピューティング プラットフォームで実行されている、WebSphere MQ ホスト アダプターを含むホスト アダプターからこれらのメッセージを受信します。  
 
 ## <a name="next-reading"></a>[次へ] の閲覧
 
 [FileAct アダプターとは](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)  
 [InterAct アダプターとは](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)  
 [BizTalk FileAct および InterAct アダプターのエンド ツー エンド チュートリアル](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)
 
 ## <a name="see-also"></a>関連項目
 [FileAct および InterAct アダプターのアーキテクチャを理解する](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)