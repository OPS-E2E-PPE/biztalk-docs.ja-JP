---
title: サンプル シナリオの情報をバック グラウンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security examples [TMA], background information
- DFD
- TMA, examples
ms.assetid: f9518fe7-9892-44f5-8e05-fe48bdb5161a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b135dc4b322a2fe09289e971021ddbb387cf2915
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530645"
---
# <a name="background-information-for-sample-scenarios"></a>サンプル シナリオの背景情報
このトピックでには、このセクションではシナリオの背景情報が含まれています。  
  
## <a name="background-for-all-scenarios"></a>すべてのシナリオの背景  
 主要な脅威モデルは、会議、前に、次のような背景情報を収集しました。 この情報は、サンプル アーキテクチャで特定されたすべての使用シナリオに適用されます。  
  
-   アーキテクチャの境界およびスコープ  
  
-   信頼と信頼されていないコンポーネント間の境界  
  
-   各コンポーネントの構成および管理モデル  
  
-   その他のコンポーネントおよびアプリケーションに関する前提条件  
  
### <a name="boundaries-and-scope-of-the-architecture"></a>アーキテクチャの境界およびスコープ  
  
-   ファイアウォール 2 保護サーバーとアプリケーション E ビジネス ドメインの境界ネットワークと (たとえば、企業ドメインまたはその他のアプリケーションのドメイン) 環境での他のドメインの両方。  
  
-   2 つのルートを受信したすべてのファイアウォールおよび E ビジネス ドメインへのトラフィックを送信します。  
  
-   すべてのユーザー グループと BizTalk Server 環境にアクセスするアカウントには、E ビジネス ドメイン内のグローバル グループがある場合があります。  
  
-   アクセスは、ホスト インスタンスのサービス アカウントに制限されていますすべてのアプリケーション ファイル、SQL、またはメッセージ キューは受信サーバーにメッセージをドロップします。BizTalk Server、エンタープライズ シングル サインオン (SSO)、および Windows 管理者とします。  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a>信頼と信頼されていない企業間の境界  
  
-   2 つのルートを受信したすべてのファイアウォールおよび E ビジネス ドメインへのトラフィックを送信します。  
  
-   BizTalk Server 内のアプリケーション間のセキュリティ境界としてさまざまな BizTalk ホストを使用します。  
  
-   アプリケーション (たとえば、サード パーティのコンポーネント信頼されたホストで実行しないで) 内でコードを信頼する場合にのみ、信頼されたホストを使用します。  
  
### <a name="configuration-and-administration-model-for-each-component"></a>各コンポーネントの構成および管理モデル  
 **構成モデル:**  
  
- BizTalk Server ランタイム コンポーネントは、BizTalk サーバーでのみインストールされます。  
  
- マスター シークレット サーバーには、追加のコンポーネントがありません。  
  
- SQL Server には、すべての BizTalk Server データベースが含まれています。  
  
- 境界ネットワーク内のサーバーには、BizTalk Server コンポーネントがありません。  
  
- 管理クライアントを使用して、E ビジネス ドメインのすべてのサーバーを管理します。  
  
  **管理モデル:**  
  
- デスクトップ (またはラップトップ) からは、管理者は、(ターミナル サービスまたはリモート デスクトップ接続を使用して) 管理ツールを使用したコンピューターに接続します。 ツールが管理されているコンピューターに接続すると、管理者後、管理者は、すべてのサーバーとドメイン内のアプリケーションを管理するのに、BizTalk 管理ツールを使用できます。  
  
### <a name="assumptions-about-other-components-and-applications"></a>その他のコンポーネントおよびアプリケーションに関する前提条件  
 その他のすべてのアプリケーションおよび BizTalk Server 環境と対話するコンポーネント (たとえば、境界ネットワーク) で、E ビジネス ドメイン以外では。 これらのアプリケーションとコンポーネント、および BizTalk Server 環境からのトラフィックは、ファイアウォール 2 経由で移動します。  
  
 BizTalk Server のすべてのサード パーティ製アプリケーションは、信頼できるベンダーから取得されます。  
  
### <a name="data-flow-diagrams"></a>データ フロー ダイアグラム  
 各使用シナリオの背景情報の最後の要素は、データ フロー ダイアグラム (DFD) です。 DFD は、アーキテクチャを介したデータの流れを示しています。 各シナリオでは、個別の DFD が。 このドキュメントでは、データ フローの図は、次の図に示すように要素を含めます。  
  
 **図 1 DFD の要素**  
  
 ![DFD の要素](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")  
  
## <a name="background-for-adapter-scenarios"></a>アダプタ シナリオの背景  
 次に基づいた使用シナリオがわかりました、サンプル アーキテクチャでは、アダプターの一部では、ボックスを使用することができます。  
  
- HTTP アダプタと SOAP (Web サービス) アダプタ シナリオ  
  
- BizTalk メッセージ キュー アダプタ シナリオ  
  
- ファイル アダプタ シナリオ  
  
- FTP アダプタ シナリオ  
  
  各シナリオでは、脅威モデル分析を完了する手順に従いました。  
  
- 背景情報の収集  
  
- 脅威モデルの作成と分析  
  
- 脅威の確認  
  
- 緩和方法とテクノロジの特定  
  
  各シナリオでは、さまざまな攻撃を表すことが脅威のレベルの一般的な評価の作成を試みました。 ただし、環境が、ある特定の脅威は異なる度合いによりもお勧めします可能性があります。 すべてのセキュリティ シナリオでは、独自のデータは最も堅牢な脅威レベルを判断すると、ことをお勧めをガイドとして、分析と結果を使用して、独自の分析が実施します。  
  
  背景情報: データ フロー ダイアグラム (DFD) を除くの使用シナリオすべて同じです。 次のセクションでは、各シナリオの DFD を示しています。  
  
## <a name="see-also"></a>参照  
 [脅威モデル分析](../core/threat-model-analysis.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)   
 [セキュリティの計画](../core/planning-for-security.md)   
 [中小企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)