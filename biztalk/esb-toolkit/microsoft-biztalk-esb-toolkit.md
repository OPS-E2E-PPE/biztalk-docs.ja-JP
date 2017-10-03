---
title: "Microsoft BizTalk ESB Toolkit |Microsoft ドキュメント"
description: "概要、一般的なシナリオ、および BizTalk Server で ESB Toolkit のコンポーネント"
caps.latest.revision: "14"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17ffaebc-7e33-4de8-8e94-109cd5d16ca0
ms.author: mandia
ms.openlocfilehash: 1763ed4bb7f090b91565c3a5f5f480d2c081b48c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="microsoft-biztalk-esb-toolkit"></a>Microsoft BizTalk ESB Toolkit
![BizTalk ESB Toolkit ロゴ](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")  
  
## <a name="summary"></a>概要  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]疎結合のメッセージング アーキテクチャをサポートします。 BizTalk Server には、メッセージング アプリケーション用の強力なパブリッシュ/サブスクライブ メカニズムが組み込まれています。このメカニズムは、サブスクリプションを作成および入力することによって機能し、サービス指向アーキテクチャ (SOA) アプリケーション向けの、高い効率と拡張性を備えたプラットフォームを提供します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]軽量なサービスの日程ベースのサービスの呼び出しが組み込まれた信頼性の高い、接続されている、サービス指向のアプリケーションの構築に重点を置いての新機能の範囲を指定する BizTalk Server の機能を拡張コンポジション、動的解決のエンドポイントとマップ、Web サービスと ws-* の統合、障害管理とレポート、およびサードパーティの SOA 管理ソリューションと統合します。  
  
## <a name="overview"></a>概要  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アーキテクチャに関するガイダンス、パターン、および BizTalk Server と .NET Framework のコンポーネントの Enterprise Service Bus (ESB)、Microsoft プラットフォームで開発を簡略化し、拡張するマイクロソフトの顧客のコレクションを提供します。独自のメッセージングおよび統合ソリューションです。  
  
## <a name="common-scenarios"></a>一般的なシナリオ  
 Enterprise Service Bus (ESB) という用語は、サービス指向アーキテクチャ (SOA) を実現するためのインフラストラクチャの実装というコンテキストにおいて広く利用されています。 しかし、SOA の開発にかかわった実際の経験から、ESB は包括的なサービス指向インフラストラクチャ (SOI) を構成する多数の構成要素の 1 つにすぎないことが判明しています。 ESB という用語は数多くの多様な方向に変貌し、その定義は、個々の ESB ベンダーおよび統合プラットフォーム ベンダーによって、また、特定の SOA イニシアティブの要件によって異なります。  
  
 Microsoft が SOA 実装の多数の実例から得た経験に基づいて、ESB を次のように考えることができます。つまり、ESB は、従来のエンタープライズ アプリケーション統合 (EAI)、メッセージ指向ミドルウェア、Web サービス、.NET と Java の相互運用性、ホスト システム統合、サービス レジストリおよび資産リポジトリとの相互運用性をベースとするアーキテクチャ パターンのコレクションです。  
  
 図 1 は、ESB アーキテクチャを提供できる相互接続の種類の概要を示します。  
  
 ![ESB の概要](../esb-toolkit/media/esboverview.gif "ESBOverview")  
  
 **図 1**  
  
 **接続の高度な例は、Enterprise Service Bus アーキテクチャを提供**  
  
## <a name="audience-requirements"></a>利用者の要件  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を使用するその他のソリューションや、Microsoft BizTalk Server ソリューションを作成する開発者のためのものでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントです。 フル活用するために、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]開発者の知識し、次の操作が発生する必要があります。  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
-   Microsoft .NET 開発手法 (ASP.NET Web サービスおよび .NET Framework コンポーネントの開発など)  
  
## <a name="design-goals"></a>設計目標  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一連の相互運用をサポートし、メッセージ ベースのエンタープライズ アプリケーションを構築するが容易疎結合のメッセージング環境を実装するコンポーネントで構成されています。 サービスとコンポーネントは、次の 7 つのカテゴリに必然的に分類されます。  
  
-   **Web サービス**: 公開されるため、itinerary 処理では、例外管理、エンドポイント、マップ、BizTalk Server の処理、およびメッセージの変換の解像度などの内部のサービスです。  
  
-   **Itinerary サービス**: 行程ベースのルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 行程ベースのルーティングのカスタム サービスを作成することができます。  
  
-   **Itinerary 上のランプします。** これら外部メッセージを受信、メッセージごとに適切な旅程をアタッチ itinerary、処理を行います。使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーと動的解決のエンドポイントとメタデータのプロバイダー フレームワークのアダプターです。  
  
-   **ランプで**: これらの形式と HTTP、JMS、WMQ、FTP、フラット ファイル、および XML などのトランスポートの範囲内で外部メッセージの受信します。 一般的な BizTalk Server は必要に応じて使用する受信場所、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用機能のパイプライン コンポーネント、および[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーと動的解決のエンドポイントとメタデータのプロバイダー フレームワークのアダプターです。  
  
-   **傾斜オフ**: これらの形式と SOAP、WCF、JMS、WMQ、FTP、HTTP、フラット ファイル、XML、またはその他のカスタム形式などのトランスポートを使用してメッセージ配信用の送信ポートを実装します。 一般的な BizTalk Server 動的送信ポートを直接バインドをメッセージ ボックスに使用されているとオプションでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用機能のパイプライン コンポーネント、および[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーとエンドポイントの動的解決のアダプターのプロバイダー フレームワークメタデータ。  
  
-   **例外管理フレームワーク**: 例外 Web サービス、例外管理 API が含まれます、強化、コンポーネントの処理、および例外の詳細を ESB の管理ポータルに渡します。  
  
-   **管理ポータルの ESB** : これにより、レジストリのプロビジョニング、例外の仲介、アラートの通知、および分析します。  
  
 によって実装された機能を利用してこれらのコンポーネントとサービスの多く[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション、変換、およびビジネス ルール エンジンと、メッセージ ボックス データベースなどです。 図 2 はのカテゴリの概略を示しています。コンポーネントと各カテゴリ内で発生する一般サービスコア BizTalk Server のシステム コンポーネントによって使用されると、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 ![ESB アーキテクチャ](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
 **図 2**  
  
 **アーキテクチャとのコンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB Toolkit の動作  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージを受け取り、演算を実行して、通常 (必ずではありませんが) 変換、配信、またはその他のカスタム定義プロセスなどのプロセスを実行することによってです。 必要な操作を指定するには、中心となる処理コンポーネントに、関連付けられた指示またはメタデータを格納するメッセージが必要です。その指示またはメタデータにより、メッセージの内容に対して適用するプロセスおよび実行するタスクが定義されます。  
  
 これにより、サービス間の疎結合これは、ESB メッセージごとに、特定の処理の知識が必要ないことを意味します。 ESB に必要な情報は、発生する可能性のあるプロセスの範囲と、各プロセスを適用する方法だけです。 使用可能なプロセスおよびプロセスと指示のマッピングをメッセージ内に指定するための広範囲なオプションが用意されているので、コードの変更やコンポーネントの再展開を必要とせずに動作を構成および調整するための柔軟なメカニズムが実現されています。  
  
## <a name="in-this-section"></a>このセクションの内容

- [インストールして、Microsoft BizTalk ESB Toolkit の構成](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [BizTalk ESB Toolkit の概要](introduction-to-the-biztalk-esb-toolkit.md)

- [作業の開始し、BizTalk ESB Toolkit を理解します。](getting-started-with-the-biztalk-esb-toolkit.md)

- [主要なシナリオおよび開発タスク](key-scenarios-and-development-tasks.md)

- [Itinerary designer を使用して日程を作成します。](creating-itineraries-using-itinerary-designer.md)

- [BizTalk ESB Toolkit のサンプル アプリケーション](biztalk-esb-toolkit-sample-applications.md)

- [変更して、BizTalk ESB Toolkit の拡張](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [BizTalk ESB Toolkit を使用した管理](administration-with-the-biztalk-esb-toolkit.md)

- [SOA ガバナンスの統合](soa-governance-integration.md)

- [BizTalk ESB Toolkit のトラブルシューティング](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a>関連トピック  
  
-   [BizTalk サービス指向ソリューション](../core/service-oriented-solution.md)

- [BizTalk Server と Web サービスの使用](../core/using-web-services.md)  