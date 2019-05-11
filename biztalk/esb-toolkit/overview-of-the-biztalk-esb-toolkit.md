---
title: BizTalk Server で ESB Toolkit の概要 |Microsoft Docs
description: ESB Toolkit と BizTalk Server でその機能の説明
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
ms.openlocfilehash: c334e5c4404492fbda28c301d8806471b25623ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400047"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a>BizTalk ESB Toolkit とは

## <a name="overview"></a>概要
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]疎結合のメッセージング アーキテクチャをサポートするために BizTalk Server の機能を拡張します。 ほとんどの開発者は、コードを使用した、手順、またはオブジェクト指向開発パラダイムに慣れています。 ただし、BizTalk ソリューションの開発を始めるには、ときに開発者を BizTalk Server のメッセージ指向の機能が見落とされがちに傾向があります。  
  
 BizTalk Server には、サブスクリプションの入力を作成して動作する強力なパブリッシュ/サブスクライブのメカニズムが含まれています。 BizTalk メッセージ ボックス データベースに新しいメッセージが到着すると、メッセージ エージェントはサブスクライバーを識別して、サブスクリプションを持つ任意のエンドポイントにメッセージを送信します。 関連付けられた受信のメッセージは、待機しているまたは送信ポートの作成 (など、型は、受信メッセージのプロパティに一致するフィルター条件を持つ、受信ポートにオーケストレーションをバインドを含む、いくつかの方法でサブスクリプションを作成できます。ポイント、またはルーティング可能なプロパティの値)。  
  
 BizTalk Server では、この効率的でスケーラブルな方法を提供し、一連の不連続のサブ プロセスを作成して、シーケンスの詳細について心配せずに、その呼び出しをトリガーするメッセージの種類を定義ができます。 メッセージの到着によって開始されたプロセスは、メッセージの処理を実行します。メッセージを処理した後、これは、1 つまたは複数のサブプロセスをアクティブ化できるメッセージ ボックス データベースを同じまたは別のメッセージを提供できます。  
  
 Microsoft では、Windows Server、.NET Framework では、BizTalk Server など、包括的なサービス指向のインフラストラクチャを構築するために必要な重要な構成要素を提供します。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次を含む、ESB の最も一般的なサービスの基礎を提供するため、BizTalk Server に基づきます。  
  
-   メッセージのルーティング  
  
-   メッセージの検証  
  
-   メッセージの変換  
  
-   接続用の拡張可能なアダプター フレームワーク  
  
-   サービス オーケストレーション  
  
-   ビジネス ルール エンジン  
  
-   ビジネス アクティビティの監視  
  
-   Web サービスと ws-* (WCF アダプター) の統合  

## <a name="core-capabilities"></a>コア機能  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]さまざまな堅牢な接続されている、サービス指向アプリケーションの構築に重点を置いた新しい機能を提供する BizTalk Server の機能を拡張します。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk Server コンポーネントを接続できる作業の個々 の単位として扱われます、必要に応じて形成疎結合されたソリューション。 コア機能の一部を次にする、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk Server の機能を強化するために提供します。  
  
- **ポリシーに基づく仲介します。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。  
  
  - メッセージの発行時に軽量のサービスの構成をサポートするスケジュールに基づくルーティングを提供します。 このアプローチには、サービス エンドポイントとサービスのレジストリまたはビジネス ルール ポリシーを使用してメッセージのルーティングで仲介要件の動的な検出ができます。  
  
  - スケジュールに基づくが動的に解決され、メッセージの後に、メッセージ コンテキストに追加するサーバー側のスケジュールを使用してルーティングが受信されるは、ポリシーの集中化のサポートを追加します。 ユーザーに対する要求のルーティング方法の完全に対応していないクライアントからのメッセージの処理を中央の場所での旅程を管理できます。  
  
  - 拡張のバージョンを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワーク、エンドポイントと変換の要件の動的な解決を有効にする; 効果的に分離され、サービスのコンシューマーです。  
  
- **システムを接続します。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。  
  
  -   XML メッセージの名前空間の正規化のパイプライン コンポーネントを提供します。  
  
  -   統合 JMS WebSphere MQ アダプターを通じて BizTalk Server にします。  
  
  -   サービスの動的な集計、メッセージのルーティング、メッセージの検証、およびメッセージの変換を有効にするメッセージ交換パターンが容易になります。  
  
  -   レジストリと UDDI 3.0 を使用して統合をリポジトリからサービス エンドポイントの検出をサポートします。  
  
  -   BizTalk Server の WCF カスタム BizTalk アダプターを使用して基幹業務 (LOB) アダプターを通じてメッセージのルーティングをサポートします。  
  
- **管理および監視します。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。  
  
  -   例外管理フレームワークとツールを提供します。  
  
  -   メッセージの修復と再送信、管理ポータルを使用できるサンプル アプリケーションに付属しています。 この Web アプリケーションは、特定のエラーが発生した場合にもカスタマイズ可能な電子メール通知をサポートします。  
  
  -   BizTalk Server のエンドポイントとレジストリの統合、管理、および発行できます。  
  
  -   サーバー側のバージョン管理されたスケジュールのリポジトリを集中管理を提供します。  
  
  -   BizTalk Server アプリケーションのレポートと分析をサポートします。  
  
  -   これには、開始時刻、終了時刻、およびサービス仲介シーケンスなど、スケジュール サービスの実行を追跡するために、ビジネス アクティビティ監視コンポーネントが含まれます。  
  
- **SOA ガバナンス。** [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。  
  
  -   AmberPoint と SOA ソフトウェアから BizTalk Server 用の組み込み管理エージェントなど、サードパーティの SOA ガバナンス ソリューションと統合します。  

> [!TIP]
> [Understanding BizTalk Server](../core/understanding-biztalk-server.md)メッセージング エンジンでは、その他の詳細を提供します。

## <a name="get-some-help"></a>いくつかのヘルプを表示します。
いくつかのヘルプを取得し、ヘルプにある他のユーザー、 [BizTalk ESB Toolkit フォーラム](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409)します。

## <a name="next-steps"></a>次のステップ
[BizTalk ESB Toolkit の内容](contents-of-the-biztalk-esb-toolkit.md)  
