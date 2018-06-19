---
title: サンプル シナリオの情報をバック グラウンド |Microsoft ドキュメント
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
ms.openlocfilehash: 13dbb247e42116d5b308170d5ef365ed9f20d793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231738"
---
# <a name="background-information-for-sample-scenarios"></a>サンプル シナリオの背景情報
このトピックには、このセクションで紹介するシナリオの背景情報が記載されています。  
  
## <a name="background-for-all-scenarios"></a>すべてのシナリオの背景  
 主要な脅威モデルについてのミーティングを行う前に、次の背景情報を収集しました。 この情報は、サンプル アーキテクチャで特定されたすべての使用シナリオに適用されます。  
  
-   アーキテクチャの境界およびスコープ  
  
-   信頼されたコンポーネントと信頼されていないコンポーネントの境界  
  
-   各コンポーネントの構成および管理モデル  
  
-   他のコンポーネントおよびアプリケーションに関する前提  
  
### <a name="boundaries-and-scope-of-the-architecture"></a>アーキテクチャの境界およびスコープ  
  
-   ファイアウォール 2 により、E ビジネス ドメイン内のサーバーとアプリケーションを境界ネットワークおよび環境内の他のドメイン (企業ドメインや他のアプリケーションのドメインなど) から保護できます。  
  
-   ファイアウォール 2 から E ビジネス ドメインにすべての着信トラフィックと送信トラフィックがルーティングされます。  
  
-   BizTalk Server 環境にアクセスするすべてのユーザー グループとアカウントは E ビジネス ドメイン内のグローバル グループに属している必要があります。  
  
-   アクセスは、ホスト インスタンスのサービス アカウントと、ファイル、SQL、またはメッセージ キューの受信サーバーにメッセージをドロップする任意のアプリケーション、および BizTalk Server、エンタープライズ シングル サインオン (SSO)、Windows の管理者に制限されます。  
  
### <a name="boundaries-between-trusted-and-untrusted-companies"></a>信頼された企業と信頼されていない企業の境界  
  
-   ファイアウォール 2 から E ビジネス ドメインにすべての着信トラフィックと送信トラフィックがルーティングされます。  
  
-   BizTalk Server 内のアプリケーション間でセキュリティの境界としてさまざまな BizTalk ホストを使用します。  
  
-   アプリケーション内のコードを信頼する場合に限り、信頼されたホストを使用します (たとえば、信頼されたホストではサード パーティ コンポーネントを実行しないでください)。  
  
### <a name="configuration-and-administration-model-for-each-component"></a>各コンポーネントの構成および管理モデル  
 **構成モデル:**  
  
-   BizTalk Server ランタイム コンポーネントは、BizTalk Server のみにインストールされます。  
  
-   マスタ シークレット サーバーには追加コンポーネントはありません。  
  
-   SQL Server には、すべての BizTalk Server データベースが含まれます。  
  
-   境界ネットワーク内のサーバーには、BizTalk Server コンポーネントはありません。  
  
-   管理クライアントは、E ビジネス ドメイン内のすべてのサーバーを管理するために使用されます。  
  
 **管理モデル:**  
  
-   管理者は、デスクトップ (またはラップトップ) から管理ツールがあるコンピュータに (ターミナル サービスまたはリモート デスクトップ接続を使用して) 接続します。 管理者は管理ツールのあるコンピュータに接続した後、BizTalk 管理ツールを使用してドメイン内のすべてのサーバーとアプリケーションを管理できます。  
  
### <a name="assumptions-about-other-components-and-applications"></a>他のコンポーネントおよびアプリケーションに関する前提  
 BizTalk Server 環境と連携する他のすべてのアプリケーションとコンポーネントは、E ビジネス ドメイン以外のドメイン (境界ネットワークなど) にあります。 これらのアプリケーションとコンポーネント、および BizTalk Server 環境からのトラフィックは、ファイアウォール 2 経由で処理されます。  
  
 BizTalk Server のサード パーティ アプリケーションの製造元は、信頼されたベンダです。  
  
### <a name="data-flow-diagrams"></a>データ フロー ダイアグラム  
 各使用シナリオの背景情報の最後の要素は、データ フロー ダイアグラム (DFD) です。 DFD は、アーキテクチャ内のデータ フローがどのようなものであるかを示します。 各シナリオには個別の DFD があります。 このドキュメントのデータ フロー ダイアグラムには、次の図に示されている要素が含まれています。  
  
 **図 1 DFD の要素**  
  
 ![DFD の要素](../core/media/tdi-sec-dfd-legend.gif "TDI_Sec_DFD_Legend")  
  
## <a name="background-for-adapter-scenarios"></a>アダプタ シナリオの背景  
 サンプル アーキテクチャでは、追加設定なしで使用できるいくつかのアダプタに基づく次の使用シナリオが特定されました。  
  
-   HTTP アダプタと SOAP (Web サービス) アダプタ シナリオ  
  
-   BizTalk メッセージ キュー アダプタ シナリオ  
  
-   ファイル アダプタ シナリオ  
  
-   FTP アダプタ シナリオ  
  
 各シナリオでは、次の手順に従って脅威モデル分析を完了しました。  
  
-   背景情報の収集  
  
-   脅威モデルの作成と分析  
  
-   脅威の確認  
  
-   緩和方法とテクノロジの特定  
  
 各シナリオに対して、さまざまな攻撃によって生じる可能性がある脅威のレベルに応じて、一般的な度合いの策定を試みました。 ただし、環境によっては、特定の脅威がここに示したのとは異なる度合いに相当すると提示されることがあります。 すべてのセキュリティ シナリオと同様に、脅威レベルを判断するうえで最も信頼性が高いのは独自のデータです。サンプル シナリオでの分析と結果を参考にして独自の分析を実行することをお勧めします。  
  
 背景情報については、— データ フロー ダイアグラム (DFD) を除くの使用シナリオすべて同じです。 次のセクションでは、各シナリオの DFD を示します。  
  
## <a name="see-also"></a>参照  
 [脅威モデル分析](../core/threat-model-analysis.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)   
 [セキュリティの計画](../core/planning-for-security.md)   
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)