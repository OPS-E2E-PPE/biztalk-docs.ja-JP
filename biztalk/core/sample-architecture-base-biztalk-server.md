---
title: 'サンプル アーキテクチャ: 基盤となる BizTalk Server |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- IPSec
- BizTalk Server, examples
- security, examples
- security, architecture
- IPSec, about IPSec
- BizTalk Server, architecture
- architecture, security
ms.assetid: 7ccc1ef3-670f-423f-b6ca-3d56b9bbeabf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea815c0165f58c28cea8ce7cae35fd6ed7437323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271194"
---
# <a name="sample-architecture-base-biztalk-server"></a>サンプル アーキテクチャ: 基盤となる BizTalk Server
ここでは、基盤となるサンプル アーキテクチャについて説明します。 BizTalk Server の展開の中で、アダプターに依存しないコンポーネントについて説明します。 BizTalk Server の展開に少なくともこれらのコンポーネントを含めることをお勧めします。  
  
 次の図は、基盤となる BizTalk Server サンプル アーキテクチャのコンポーネントを示しています。 これらのコンポーネントは、後半で説明するアダプター固有の BizTalk Server アーキテクチャにすべて出現します。  
  
 **図 1 の基本アーキテクチャ コンポーネント**  
  
 ![ベース アーキテクチャ コンポーネント](../core/media/tdi-sec-refarch.gif "tdi_sec_refarch _")  
  
 このサンプル アーキテクチャには、以下のセクションに記載する項目が含まれています。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク-インターネット  
  
-   この境界ネットワーク (DMZ、非武装地帯、スクリーン サブネットとも呼ばれます) には、インターネット関連のサービスを提供するサーバーが含まれています。 このドメインには、BizTalk Server、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーはありません。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク - イントラネット  
 この境界ネットワークには、イントラネット関連のサービスを提供するサーバーが含まれています。 イントラネット (企業ネットワークなど) とアプリケーションが実行されるサーバー間のセキュリティに追加の層を提供します。 インターネット境界ネットワークと同様に、イントラネット境界ネットワークには、BizTalk Server、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーは含まれません。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメインには、BizTalk Server の実装によって使用されるインフラストラクチャとアプリケーションがすべて含まれます。 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server です。** このサーバーには BizTalk Server ランタイムのインストールと、さまざまな BizTalk ホストのインスタンスが含まれています。 環境内の BizTalk Server の数は、実行されるホストの種類とパフォーマンスのニーズによって異なります。 パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。  
  
-   **マスター シークレット サーバーです。** このサーバーは、エンタープライズ シングル サインオン (SSO) マスター シークレット サーバーです。 SSO システムが SSO データベース内のデータの暗号化に使用するマスター シークレット (暗号化キー) が保存されています。  
  
-   **SQL Server。** このサーバーには、BizTalk データベースが含まれます。  
  
    > [!IMPORTANT]
    >  フェールオーバー保護のために、各 BizTalk データベースをクラスター化することをお勧めします。 Microsoft SQL Server フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216)です。  
  
    > [!NOTE]
    >  パフォーマンスのニーズによっては、BizTalk データベースを SQL Server が実行されている複数のコンピューターに分散することが必要になる場合があります。  
  
-   **ドメイン コント ローラー。** このサーバーは E ビジネス Active Directory ドメインをホストします。 BizTalk Server へのアクセスが必要なすべてのグループと個別のアカウントについての情報が含まれます。  
  
-   **管理ツールです。** このドメインのサーバーの 1 つは、管理ツール (BizTalk 管理コンソールおよびエンタープライズ シングル サインオン (SSO) 管理ユーティリティ) をホストしています。  
  
## <a name="firewalls-and-domains"></a>ファイアウォールとドメイン  
 図 1 では、Forefront Threat Management Gateway (TMG) 2010 サーバーがソフトウェア ファイアウォールの役割を担い、これらの各ドメインを保護すると共に境界となっています。 また、E ビジネス ドメインには独自のドメイン コントローラーがあり、このドメインは他のドメインとの信頼関係がありません。 ドメインと信頼関係に対してファイアウォールを構成する方法の詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230)です。  
  
 サンプル アーキテクチャには 2 つのファイアウォールがあります。  
  
-   **ファイアウォール 1。** このファイアフォールには 3 つのネットワーク インターフェイスがあり、インターネット、イントラネット、および境界ネットワークからのトラフィックをルーティングします。  
  
-   **ファイアウォール 2。** このファイアウォールはデュアルホームです。境界ネットワーク (インターネットとイントラネットの両方) および E ビジネス ドメインからのトラフィックをルーティングします。  
  
 境界ネットワーク内のコンピューターはどのドメインにも属していないので、相互通信することはありません。  
  
## <a name="ipsec"></a>IPsec (IPsec)  
 Internet Protocol security (IPSec) を使用して、E ビジネス ドメイン内のすべてのサーバー間の通信をセキュリティで保護することをお勧めします。 IPsec 規則は次のとおりです。  
  
-   BizTalk Server とドメイン コントローラー間の認証されたトラフィックを許可します。  
  
-   BizTalk Server と管理ツール サーバー間の認証されたトラフィックを許可します。  
  
-   BizTalk Server とマスター シークレット サーバー間の認証されたトラフィックを許可します。  
  
-   BizTalk Server と SQL Server 間の認証されたトラフィックを許可します。  
  
-   マスター シークレット サーバーとドメイン コントローラー間の認証されたトラフィックを許可します。  
  
-   マスター シークレット サーバーと BizTalk Server (分離ホスト、処理ホスト、インプロセス ホスト、追跡ホスト) 間の認証されたトラフィックを許可します。  
  
-   マスター シークレット サーバーと SQL Server (SSO データベース) 間の認証されたトラフィックを許可します。  
  
-   ドメイン コントローラーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。  
  
-   管理ツール サーバーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。  
  
 ドメイン内に BizTalk Server、SQL Server、マスター シークレット サーバー、または管理ツール サーバーへのアクセスが不要なその他のアプリケーションがある場合、それらのアプリケーションと該当するサーバー間のトラフィックをブロックしてください。  
  
## <a name="see-also"></a>参照  
 [セキュリティの計画](../core/planning-for-security.md)   
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)