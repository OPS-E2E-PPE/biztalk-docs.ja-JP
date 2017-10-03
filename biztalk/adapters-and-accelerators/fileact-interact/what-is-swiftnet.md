---
title: "SWIFTNet とは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b074385-352c-40f4-b73e-1891c627aa4e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1668c1f568a6cfb853957b3598b41f1cbdf6e33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-swiftnet"></a>SWIFTNet とは何ですか。
汎用の財務の業界の業界標準のソリューションとしては、SWIFTNet はグローバル財務コミュニティに参加しているすべての金融機関の接続されているすべてのアプリケーションへのアプリケーションに依存しない、1 つのウィンドウ インターフェイスを提供します。 インフラストラクチャの技術的な制限ではなく、ビジネス ポリシー決定の各サービス管理者では、実際のアクセスが制御されます。  
  
 SWIFTNet は、ビジネス継続性と災害復旧制度化された境界を越えるミッション クリティカルな財務アプリケーションのインフラストラクチャを維持するための基礎を提供します。 SWIFTNet はミッション クリティカルな財務ソフトウェア ソリューションの相互運用性の制度化されたコミュニティ要件を満たすために設計されています。  
  
 相互接続されたビジネス アプリケーションに次を提供 SWIFTNet:  
  
-   インフラストラクチャの信頼性の保証  
  
-   可用性  
  
-   ロール ベースおよび役割に基づいたのアクセス制御  
  
-   送信者とメッセージの認証  
  
-   メッセージの整合性  
  
-   機密性  
  
-   否認不可のサポート  
  
-   メッセージの検証  
  
-   ストア アンド フォワード  

SWIFTNet を使用して**SWIFTNet リンク**(SNL) SWIFTNet サービス、および使用のアプリケーション プログラミング インターフェイスとして、 **SWIFTAlliance ゲートウェイ**接続し、使いやすさ。 このトピックでこれらのリソースに関する詳細を参照してください。

## <a name="swiftnet-link-overview"></a>SWIFTNet リンクの概要

ビジネス ソフトウェア アプリケーションにアクセスして SWIFTNet サービスを使用する SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) を使用します。 SNL は、SWIFTNet に必須のネットワーク インターフェイスです。 SWIFTNet には、すべての外部インターフェイスに対して SNL が必要です。 SNL には、メッセージング、セキュリティ、およびサービス管理機能をサポートするバック グラウンド プロセスも含まれています。 SNL は SWIFTAlliance WebStation と SWIFTAlliance ゲートウェイ (SAG) に組み込まれます。  
  
 SNL は、ビジネス アプリケーションのコンポーネント間の疎結合のクライアント/サーバー関係を確立します。 メソッドまたは関数を直接呼び出すことではなく、相互作用がメッセージ指向: 構造化されたメッセージがクライアントとサーバー間で渡されます。 一般に SWIFTNet サービス用に設計されたビジネス アプリケーションは、クライアントとサーバーのセットで構成されます。 同じクライアントまたは同じサーバー プロセスに複数回を開始できます。 同じアプリケーションの受信メッセージ要求のインスタンスの配信にするプロセスを予測することはできませんに注意してください。 クライアント プロセス内で複数のスレッドは、SwCall API 関数を呼び出すことができます。 サーバー プロセスが複数のスレッドも; があることができます。ただし、1 つのスレッドは SwCallback を呼び出すことができます。 クライアントとサーバー プロセスは、同じプロセス内で組み合わせて使用できません。  
  
 SNL は、一連の高可用性と高スループットの環境用に設計されたトランスポート レベルの機能を提供します。 次のような機能があります。  
  
-   負荷分散  
  
-   場所の透過性とルーティング、基になるトランスポート テクノロジからのアプリケーション コンポーネントを保護できます。  
  
-   トランスポート レベルの認証および機密性、SNL 内にパッケージ化し、アプリケーションに透過的に提供  
  
-   セキュリティ関数がアプリケーション ソフトウェアはビジネスによってエンド ツー エンド セキュリティ (ユーザーのアプリケーション ユーザーのアプリケーションに) を確立することが必要な場合にします。  
  
 C++、または Java を使用して、ソース コード レベルでのプログラミングの観点からは、2 つの関数: SwCall と SwCallback です。 SwCall は SWIFTNet を介してサーバー アプリケーションにアクセスするクライアント アプリケーションによって使用されます。 SwCallback は SWIFTNet を介してクライアントに応答するサーバー アプリケーションによって使用されます。  
  
 SwCall および SwCallback 関数は、構造化された XML メッセージとの間の SWIFTNet を渡すことによって SWIFTNet の機能にアクセスします。 SNL には実行時に、両方のソフトウェア ライブラリが含まれています — ビジネス アプリケーションのクライアントまたはサーバーのプロセスと同じアドレス空間内で実行されるうちコード-アドレス空間を独立したプロセス (デーモンまたはサービス) が自分で実行されるとします。 ソフトウェア ライブラリは、SNL Api を通じてアクセスします。  

## <a name="swiftalliance-gateway-overview"></a>SWIFTAlliance ゲートウェイの概要
  
SWIFTAlliance ゲートウェイ (SAG) は、SWIFTNet インターフェイス製品です。 SWIFTNet リンクのすべての機能が組み込まれています。 さらに、提供いくつかのさまざまな接続と操作性機能 SWIFTNet ユーザーは、さまざまなシステムにソリューションの統合の問題を提供します。  
  
 SAG は、操作のいくつかの異なるモードをサポートします。 これらのうち、厳密な SWIFTNet リンク モードは、1 つは、for SWIFT FileAct および InterAct アダプターに特に関連します。 SWIFTNet リンクの厳格モードで、SAG は、メッセージングのインターフェイスは、これらのトピックで前述 SWIFTNet リンク インターフェイスと同等の機能を表示します。  
  
 SAG は、メッセージ コンセントレータとして機能します。 さまざまな他のアプリケーションからメッセージを受信し、SWIFTNet に通過します。 により、ビジネス アプリケーション SWIFTNet 経由でメッセージを渡すには、さまざまな異なる種類のコンピューティング プラットフォームで実行されている WebSphere MQ ホスト アダプターを含むホスト アダプターからこれらのメッセージを受け取ります。  
 
 ## <a name="next-reading"></a>[次へ] の読み取り
 
 [FileAct アダプターとは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)  
 [アダプターを操作しますか?](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)  
 [BizTalk FileAct と対話するアダプターのエンド ツー エンドのチュートリアル](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)
 
 ## <a name="see-also"></a>参照
 [FileAct を理解し、アダプターのアーキテクチャの対話](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)