---
title: "BizTalk ESB Toolkit のアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a41674f5-5ea4-4a8f-a270-b67fd6854028
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 068eddfdd2138fbc92ad4821b2eaf9491ad39000
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-the-biztalk-esb-toolkit"></a>BizTalk ESB Toolkit のアーキテクチャ
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一連の相互運用をサポートし、メッセージ ベースのエンタープライズ アプリケーションを構築するが容易疎結合のメッセージング環境を実装するコンポーネントで構成されています。 サービスとコンポーネントは、次の 7 つのカテゴリに必然的に分類されます。  
  
-   **Web サービス。** Itinerary 処理、例外管理、エンドポイントやマップの解像度などの内部サービスの公開これら[!INCLUDE[prague](../includes/prague-md.md)]操作、Universal Description, Discovery, and Integration (UDDI) の相互運用、およびメッセージの変換コンテンツ。  
  
-   **Itinerary サービスです。** これらには、変換、およびメッセージのルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます。 行程処理では、参加しているカスタムのサービスを作成できます。 これらには、変換、およびメッセージのルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます。 行程処理では、参加しているカスタムのサービスを作成できます。  
  
-   **Itinerary 上のランプします。** これら外部メッセージを受信、メッセージごとに適切な旅程をアタッチ itinerary、処理を行います。使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーと動的解決のエンドポイントとメタデータのプロバイダー フレームワークのアダプターです。  
  
-   **ランプでします。** Itinerary 上のランプとは異なりこれらの受信外部メッセージ形式と HTTP、Java Message Service (JMS)、IBM WebSphere MQ (WMQ)、ファイル転送プロトコル (FTP)、フラット ファイル、および XML などのトランスポートの範囲内です。 一般的な BizTalk Server は必要に応じて使用する受信場所、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用機能のパイプライン コンポーネント、および[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーと動的解決のエンドポイントとメタデータのプロバイダー フレームワークのアダプターです。  
  
-   **傾斜オフします。** これらの実装では、形式と WCF、JMS、WMQ、FTP、HTTP、フラット ファイル、XML、またはその他のカスタム形式などのトランスポートを使用してメッセージ配信用のポートを送信します。 一般的な BizTalk Server がメッセージ ボックスに、必要に応じて使用して直接バインドされる動的送信ポートは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用機能のパイプライン コンポーネント、および[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーとエンドポイントの動的解決のアダプターのプロバイダー フレームワークとメタデータ。  
  
-   **例外管理フレームワーク。** これには、例外 Web サービス、例外管理 API、および強化し、処理および例外の詳細を ESB の管理ポータルに渡すコンポーネントが含まれます。  
  
-   **ESB の管理ポータル。** このサンプル アプリケーションは、レジストリのプロビジョニング、例外の仲介、アラートの通知、および分析を提供します。  
  
 によって実装された機能を利用してこれらのコンポーネントとサービスの多く[!INCLUDE[prague](../includes/prague-md.md)]オーケストレーション、変換、およびビジネス ルール エンジンと、メッセージ ボックス データベースなどです。 図 1 は、カテゴリ、コンポーネント、および各カテゴリ内で発生する一般サービス概略を示します、中核となる BizTalk Server のシステム コンポーネントで使用されて、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 ![ESB アーキテクチャ](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
 **図 1**  
  
 **アーキテクチャとのコンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB Toolkit の動作  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージを受け取り、演算を実行して、通常 (必ずではありませんが) ルーティング、またはその他のカスタム変換などのプロセスを実行するには、プロセスが定義されています。 操作を指定するために必要な中核となる処理コンポーネントは、各メッセージに関連付けられている指示を含む回覧または適用するプロセスを定義するメタデータをメッセージの内容を実行するタスクを必要とします。 これらのルーティングの明細旅程と呼びます自動的に解決、中央のリポジトリから取得、できる、入り口によって受信されるときに、メッセージに添付します。  
  
 このルーティング スリップ アプローチでは、つまり、ESB メッセージごとに、特定の処理の知識が必要ないこと、サービス間の疎結合を提供します。 だけ、プロセスの可能な範囲は、新機能および各プロセスを適用する方法を理解する必要があります。 使用可能なプロセスおよびプロセスと指示のマッピングをメッセージ内に指定するための広範囲なオプションが用意されているので、コードの変更やコンポーネントの再展開を必要とせずに動作を構成および調整するための柔軟なメカニズムが実現されています。  
  
## <a name="design-patterns"></a>デザイン パターン  
 プロセスがメッセージ ボックス データベースにメッセージを格納して、サブスクライバーそれを取得して、メッセージの処理命令に基づく場所、ESB を使用するアーキテクチャでは、ステート マシンの設計パターンは、効果的に実装します。 さらに、ESB を実装し、サービス指向の方法で、一連のコア Web サービス経由で外部のアプリケーションを含むのコア機能を公開します。  
  
 BizTalk Server を設計する方法を疎結合これと[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]-ベースのアプリケーションが非常に柔軟なソリューションの生成し、-受理されました」業界のベスト プラクティスとなっています。