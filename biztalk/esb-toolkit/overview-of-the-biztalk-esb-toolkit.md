---
title: BizTalk Server で ESB Toolkit の概要 |Microsoft ドキュメント
description: BizTalk Server でどのように、ESB Toolkit の説明
caps.latest.revision: 6
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e190b34-40bc-4f27-9b4f-56e98591e1d4
ms.author: mandia
ms.openlocfilehash: 9ce0bbe3710530a63127701447db87b0a3135b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296730"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a>BizTalk ESB Toolkit は、新機能

## <a name="overview"></a>概要
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]疎結合のメッセージング アーキテクチャをサポートするために BizTalk Server の機能を拡張します。 ほとんどの開発者は、コード指向、手順、または他のオブジェクト指向開発パラダイムに慣れています。 ただし、開始時に BizTalk ソリューションを開発し、開発者を BizTalk Server のメッセージ指向の機能を見落とされる傾向があります。  
  
 BizTalk Server には、作成し、サブスクリプションで動作する強力なパブリッシュ/サブスクライブ メカニズムが含まれています。 BizTalk メッセージ ボックス データベースに新しいメッセージが到着すると、メッセージ エージェントはサブスクライバーを識別し、サブスクリプションを持つエンドポイントにメッセージを送信します。 関連付けられた受信のメッセージは、待機しているか (など、型では、受信メッセージのプロパティに一致するフィルター条件の送信ポートの作成を持つ、受信ポートにオーケストレーションをバインドなど、いくつかの方法でサブスクリプションを作成できます。ポイント、またはルーティング可能なプロパティの値)。  
  
 この効率的でスケーラブルな方法を提供する BizTalk Server 開発者は一連の個別のサブ プロセスを作成するには、その呼び出しをトリガーして、シーケンスは気にメッセージの種類を定義できます。 メッセージの到着によって開始されたプロセスは、メッセージの処理を実行します。メッセージを処理した後、メッセージ ボックス データベースに、さらに、1 つまたは複数のサブプロセスをアクティブ化できる同じまたは別のメッセージの配信、ことができます。  
  
 Microsoft では、Windows Server、.NET Framework は、BizTalk Server を含め、サービス指向の包括的なインフラストラクチャを構築するために必要なキーの構成要素を提供します。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次を含む、最も一般的な ESB サービスの基盤が提供されているために、BizTalk Server に基づきます。  
  
-   メッセージのルーティング  
  
-   メッセージの検証  
  
-   メッセージの変換  
  
-   接続の拡張可能なアダプター フレームワーク  
  
-   サービスの調整  
  
-   ビジネス ルール エンジン  
  
-   ビジネス アクティビティの監視  
  
-   Web サービスと ws-* (WCF アダプター) の統合  

## <a name="core-capabilities"></a>コア機能  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]堅牢性、接続されている、サービス指向アプリケーションの構築に重点を置いての新機能の範囲を指定する BizTalk Server の機能を拡張します。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は BizTalk Server コンポーネントを接続可能な作業の個々 の単位として処理、必要に応じてを形成疎結合されたソリューションです。 コア機能の一部を次に示しますを[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]BizTalk Server の機能を強化するために提供します。  
  
-   **ポリシーが仲介を駆動します。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。  
  
    -   メッセージの発行時に軽量なサービス構成をサポートする行程ベースのルーティングを提供します。 このアプローチでは、サービス エンドポイントとサービス レジストリまたはビジネス ルール ポリシーを使用してメッセージのルーティング仲介要件の動的な検出できます。  
  
    -   受信した日程ベースのルーティングを動的解決し、メッセージの後、メッセージ コンテキストに追加するサーバー側の日程を使用するは、ポリシーの集中化のサポートを追加します。 自身の要求のルーティング方法の完全に対応していないクライアントからのメッセージの処理を有効、一元化された場所の日程を管理します。  
  
    -   拡張のバージョンを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーとアダプター プロバイダー フレームワークでは、エンドポイントと変換の要件の動的な解決を有効にする以外の場合は、サービスからコンシューマーを効果的に分離これです。  
  
-   **システムを接続します。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。  
  
    -   メッセージの XML 名前空間を正規化するパイプライン コンポーネントを提供します。  
  
    -   その統合 JMS WebSphere MQ アダプターを通じて BizTalk Server 用です。  
  
    -   動的なサービスの集計、メッセージのルーティング、メッセージ検証、およびメッセージの変換を有効にできるメッセージ交換パターンが容易になります。  
  
    -   これは、レジストリと UDDI 3.0 を使用してリポジトリ統合からサービス エンドポイントの検出をサポートします。  
  
    -   基幹業務 (LOB) アダプターを通じて BizTalk Server の WCF カスタム BizTalk アダプターを使用して、メッセージのルーティングをサポートします。  
  
-   **管理および監視します。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。  
  
    -   例外管理フレームワークとツールを提供します。  
  
    -   メッセージの修復して、管理ポータルを使用して再送信を容易にサンプル アプリケーションとして付属します。 この Web アプリケーションは、特定のエラーが発生したときにもカスタマイズ可能な電子メール通知をサポートします。  
  
    -   これにより、BizTalk Server のエンドポイントとレジストリの統合、管理、および公開できます。  
  
    -   バージョン管理されたサーバー側の日程の一元的なリポジトリを提供します。  
  
    -   BizTalk Server アプリケーションのレポートと分析をサポートします。  
  
    -   開始時刻、終了時刻、およびサービスの仲介のシーケンスをなど、itinerary サービスの実行を追跡するためにビジネス アクティビティ監視のコンポーネントが含まれています。  
  
-   **SOA 統制します。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。  
  
    -   AmberPoint と SOA ソフトウェアから BizTalk Server の組み込み管理エージェントを含む、サード パーティの SOA 管理ソリューションと統合できます。  

> [!TIP]
> [Understanding BizTalk Server](../core/understanding-biztalk-server.md)メッセージング エンジンでは、その他の詳細を提供します。

## <a name="get-some-help"></a>いくつかのヘルプを表示します。
いくつかのヘルプを取得し、会社の他のヘルプ、 [BizTalk ESB Toolkit フォーラム](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409)です。

## <a name="next-steps"></a>次の手順
[BizTalk ESB Toolkit の内容](contents-of-the-biztalk-esb-toolkit.md)  
