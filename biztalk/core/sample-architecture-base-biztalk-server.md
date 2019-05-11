---
title: サンプル アーキテクチャ:基盤となる BizTalk Server |Microsoft Docs
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
ms.openlocfilehash: c4db442ec29ac9185bd1479219db795a9398073f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393958"
---
# <a name="sample-architecture-base-biztalk-server"></a>サンプル アーキテクチャ:基盤となる BizTalk Server
このトピックでは、基盤となるサンプル アーキテクチャについて説明します。 これには、BizTalk Server の展開でアダプターに依存しないコンポーネントについて説明します。 BizTalk Server の展開に少なくともこれらのコンポーネントがあることをお勧めします。  
  
 次の図は、サンプル アーキテクチャの基本の BizTalk Server コンポーネントを示します。 これらのコンポーネントは、以降のセクションで説明するすべてのアダプター固有 BizTalk Server アーキテクチャに表示されます。  
  
 **図 1 基本アーキテクチャ コンポーネント**  
  
 ![ベース アーキテクチャ コンポーネント](../core/media/tdi-sec-refarch.gif "tdi_sec_refarch _")  
  
 このサンプル アーキテクチャには、次のセクションで説明されている項目が含まれています。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク-インターネット  
  
-   この境界ネットワーク (DMZ、非武装地帯、およびスクリーン サブネットとも呼ばれます) には、インターネット関連のサービスを提供するサーバーが含まれています。 このドメインには、BizTalk Server、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーはありません。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク-イントラネット  
 この境界ネットワークには、イントラネット関連のサービスを提供するサーバーが含まれています。 イントラネット (企業ネットワークなど) と、アプリケーションを実行しているサーバーの間のセキュリティの追加レイヤーを提供します。 インターネットの境界ネットワークのように、イントラネット境界ネットワークに BizTalk Server が含まれていない、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーです。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメインには、すべてのインフラストラクチャと、BizTalk Server の実装で使用するアプリケーションが含まれています。 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server です。** このサーバーには、BizTalk Server ランタイムとさまざまな BizTalk ホストのインスタンスのインストール。 環境で BizTalk Server の数は、実行しているホストとパフォーマンスのニーズの種類によって異なります。 パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。  
  
-   **マスター シークレット サーバーです。** このサーバーは、エンタープライズ シングル サインオン (SSO) マスター シークレット サーバーです。 SSO システムが SSO データベース内のデータの暗号化に使用するマスター シークレット (暗号化キー) を保持します。  
  
-   **SQL Server。** このサーバーには、BizTalk データベースが含まれています。  
  
    > [!IMPORTANT]
    >  フェールオーバー保護の場合は、各 BizTalk データベースをクラスター化することをお勧めします。 Microsoft SQL Server フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216)します。  
  
    > [!NOTE]
    >  パフォーマンスのニーズに応じて、BizTalk データベースを SQL Server を実行する複数のコンピューターに分割する必要があります。  
  
-   **ドメイン コント ローラー。** このサーバーは、E ビジネス Active Directory ドメインをホストします。 すべてのグループと BizTalk Server へのアクセスを必要とする個々 のアカウントに関する情報が含まれています。  
  
-   **管理ツールです。** このドメイン内のサーバーの 1 つは、管理ツールをホストします。BizTalk 管理コンソールおよびエンタープライズ シングル サインオン (SSO) 管理ユーティリティです。  
  
## <a name="firewalls-and-domains"></a>ファイアウォールとドメイン  
 図 1 では、Forefront Threat Management Gateway (TMG) 2010 サーバーが保護し、これらの各ドメインを含めることがソフトウェア ファイアウォールとして機能します。 さらに、E ビジネス ドメインが独自のドメイン コント ローラーと、このドメインは、他のドメインを信頼しません。 ドメインと信頼関係のファイアウォールを構成する方法の詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230)します。  
  
 サンプル アーキテクチャには、2 つのファイアウォールがあります。  
  
- **ファイアウォール 1。** このファイアウォールには、次の 3 つのネットワーク インターフェイスがあります。インターネット、イントラネット、および境界ネットワークからのトラフィックをルーティングします。  
  
- **ファイアウォール 2。** このファイアウォールは、デュアル ホームです。境界ネットワーク (インターネットとイントラネットの両方) および E ビジネス ドメインからのトラフィックをルーティングします。  
  
  境界ネットワーク内のコンピューターは、任意のドメインのメンバーではないと、相互通信しません。  
  
## <a name="ipsec"></a>IPsec (IPsec)  
 E ビジネス ドメイン内のすべてのサーバー間の通信を保護するためには、インターネット プロトコル セキュリティ (IPSec) を使用することをお勧めします。 IPsec 規則は次のとおりです。  
  
- BizTalk Server とドメイン コント ローラー間の認証されたトラフィックを許可します。  
  
- BizTalk Server と管理ツール サーバー間の認証されたトラフィックを許可します。  
  
- BizTalk Server とマスター シークレット サーバー間の認証されたトラフィックを許可します。  
  
- BizTalk Server と SQL Server 間の認証されたトラフィックを許可します。  
  
- マスター シークレット サーバーとドメイン コント ローラーの間の認証されたトラフィックを許可します。  
  
- マスター シークレット サーバーと BizTalk Server (分離、処理、インプロセスで追跡ホストします。) の間の認証されたトラフィックを許可します。  
  
- マスター シークレット サーバーと SQL Server (SSO データベース) の間の認証されたトラフィックを許可します。  
  
- ドメイン コント ローラーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。  
  
- 管理ツール サーバーとドメイン内のすべてのサーバー間の認証されたトラフィックを許可します。  
  
  他のアプリケーション ドメインでそれらのアプリケーションと適切なサーバー間での BizTalk Server、SQL Server、マスター シークレット サーバー、または管理ツールのサーバーのブロック トラフィックへのアクセスを必要としない場合は。  
  
## <a name="see-also"></a>参照  
 [セキュリティの計画](../core/planning-for-security.md)   
 [中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)