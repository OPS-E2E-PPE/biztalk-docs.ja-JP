---
title: Microsoft BizTalk ESB Toolkit |Microsoft Docs
description: 概要説明、一般的なシナリオ、および BizTalk Server で ESB Toolkit のコンポーネント
caps.latest.revision: 14
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ffaebc-7e33-4de8-8e94-109cd5d16ca0
ms.author: mandia
ms.openlocfilehash: f425c02e8f869952658f93185c78474e58df304b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023400"
---
# <a name="microsoft-biztalk-esb-toolkit"></a>Microsoft BizTalk ESB Toolkit
![BizTalk ESB Toolkit ロゴ](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")  
  
## <a name="summary"></a>まとめ  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]疎結合のメッセージング アーキテクチャをサポートします。 BizTalk Server には、メッセージング アプリケーション用の強力なパブリッシュ/サブスクライブ メカニズムが組み込まれています。このメカニズムは、サブスクリプションを作成および入力することによって機能し、サービス指向アーキテクチャ (SOA) アプリケーション向けの、高い効率と拡張性を備えたプラットフォームを提供します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]さまざまな軽量のサービスのスケジュールに基づくサービス呼び出しが組み込まれた堅牢な接続されている、サービス指向のアプリケーションの構築に重点を置いた新しい機能を提供する BizTalk Server の機能を拡張合成、動的解決のエンドポイントやマップ Web サービスと ws-* の統合、障害管理とレポート、およびサードパーティの SOA 管理ソリューションとの統合。  
  
## <a name="overview"></a>概要  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アーキテクチャに関するガイダンス、パターン、および Microsoft プラットフォームでエンタープライズ サービス バス (ESB) の開発を簡略化し、Microsoft のお客様に拡張を許可する、BizTalk Server と .NET Framework のコンポーネントのコレクションを提供します。独自のメッセージングとの統合ソリューションです。  
  
## <a name="common-scenarios"></a>一般的なシナリオ  
 Enterprise Service Bus (ESB) という用語は、サービス指向アーキテクチャ (SOA) を実現するためのインフラストラクチャの実装というコンテキストにおいて広く利用されています。 しかし、SOA の開発にかかわった実際の経験から、ESB は包括的なサービス指向インフラストラクチャ (SOI) を構成する多数の構成要素の 1 つにすぎないことが判明しています。 ESB という用語は数多くの多様な方向に変貌し、その定義は、個々の ESB ベンダーおよび統合プラットフォーム ベンダーによって、また、特定の SOA イニシアティブの要件によって異なります。  
  
 Microsoft が SOA 実装の多数の実例から得た経験に基づいて、ESB を次のように考えることができます。つまり、ESB は、従来のエンタープライズ アプリケーション統合 (EAI)、メッセージ指向ミドルウェア、Web サービス、.NET と Java の相互運用性、ホスト システム統合、サービス レジストリおよび資産リポジトリとの相互運用性をベースとするアーキテクチャ パターンのコレクションです。  
  
 図 1 は、ESB アーキテクチャを提供する相互接続の種類の概要を示します。  
  
 ![ESB の概要](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **図 1**  
  
 **接続の高度な例は、Enterprise Service Bus のアーキテクチャを提供**  
  
## <a name="audience-requirements"></a>利用者の要件  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Microsoft BizTalk Server ソリューションまたはを使用するその他のソリューションを作成する開発者のためのものでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネント。 フル活用するために、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]開発者の知識を持っているし、次の操作が発生する必要があります。  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
- Microsoft .NET 開発手法 (ASP.NET Web サービスおよび .NET Framework コンポーネントの開発など)  
  
## <a name="design-goals"></a>設計目標  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一連をサポートし、メッセージ ベースのエンタープライズ アプリケーションを構築しやすく疎結合メッセージング環境を実装するコンポーネントの相互運用で構成されています。 サービスとコンポーネントは、次の 7 つのカテゴリに自然な分類されます。  
  
- **Web サービス**: これら itinerary 処理、例外管理、エンドポイント、マップ、BizTalk Server の操作、およびメッセージの変換の解像度などの内部サービスを公開します。  
  
- **スケジュール サービス**: スケジュールに基づくルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。 スケジュールに基づくルーティングのカスタム サービスを作成することができます。  
  
- **スケジュール オンランプします。** これら外部メッセージを受信、メッセージごとに適切なスケジュールをアタッチおよびスケジュールの処理を実行使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。  
  
- **オンランプ**: 範囲の形式とトランスポートで HTTP、JMS、WMQ、FTP、フラット ファイル、XML などの外部のメッセージが表示されるこれらします。 一般的な BizTalk Server は必要に応じて使用する受信場所、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。  
  
- **オフランプ**: これらの形式と SOAP、WCF、JMS、WMQ、FTP、HTTP、フラット ファイル、XML、またはその他のすべてのカスタム形式などのトランスポートを使用してメッセージの配信の送信ポートを実装します。 通常の BizTalk Server の動的送信ポートを直接バインドされたメッセージ ボックスに、必要に応じて使用するには、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのエンドポイントの動的解決のためのプロバイダー フレームワークメタデータ。  
  
- **例外管理フレームワーク**: 例外 Web サービスを例外管理 API が含まれます、強化、コンポーネントの処理、および例外の詳細を ESB 管理ポータルに渡します。  
  
- **ESB 管理ポータル**: これにより、レジストリのプロビジョニング、例外の仲介、アラート通知、および分析します。  
  
  大部分のこれらのコンポーネントとサービスによって実装される機能に依存して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション、変換、およびビジネス ルール エンジンと、メッセージ ボックス データベースなどです。 図 2 は、カテゴリ; の概略を示しています。コンポーネントと各カテゴリ内で発生する通常のサービスで使用されるコアの BizTalk Server システム コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
  ![ESB アーキテクチャ](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
  **図 2**  
  
  **アーキテクチャとのコンポーネント、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB Toolkit の動作  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージを受け取り、演算を実行して、おそらく (が常にではありません) など、変換、配信、またはその他のカスタム定義プロセスのプロセスを実行することによって。 必要な操作を指定するには、中心となる処理コンポーネントに、関連付けられた指示またはメタデータを格納するメッセージが必要です。その指示またはメタデータにより、メッセージの内容に対して適用するプロセスおよび実行するタスクが定義されます。  
  
 このアプローチは、サービス間の疎結合を提供します。これは、ESB メッセージごとに、特定の処理に関する予備知識が必要ないことを意味します。 ESB に必要な情報は、発生する可能性のあるプロセスの範囲と、各プロセスを適用する方法だけです。 使用可能なプロセスおよびプロセスと指示のマッピングをメッセージ内に指定するための広範囲なオプションが用意されているので、コードの変更やコンポーネントの再展開を必要とせずに動作を構成および調整するための柔軟なメカニズムが実現されています。  
  
## <a name="in-this-section"></a>このセクションの内容

- [インストールして、Microsoft BizTalk ESB Toolkit の構成](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [BizTalk ESB Toolkit について](introduction-to-the-biztalk-esb-toolkit.md)

- [作業の開始し、BizTalk ESB Toolkit を理解します。](getting-started-with-the-biztalk-esb-toolkit.md)

- [主要なシナリオおよび開発タスク](key-scenarios-and-development-tasks.md)

- [Itinerary designer を使用してスケジュールを作成します。](creating-itineraries-using-itinerary-designer.md)

- [BizTalk ESB Toolkit サンプル アプリケーション](biztalk-esb-toolkit-sample-applications.md)

- [変更して、BizTalk ESB Toolkit の拡張](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [BizTalk ESB Toolkit による管理](administration-with-the-biztalk-esb-toolkit.md)

- [SOA ガバナンス統合](soa-governance-integration.md)

- [BizTalk ESB Toolkit のトラブルシューティング](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a>関連トピック  
  
-   [BizTalk サービス指向ソリューション](../core/service-oriented-solution.md)

- [BizTalk Server と Web サービスの使用](../core/using-web-services.md)  