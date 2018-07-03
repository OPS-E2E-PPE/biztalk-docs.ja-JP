---
title: BizTalk ESB Toolkit のアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41674f5-5ea4-4a8f-a270-b67fd6854028
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a701b2c0170b8687e48ff61c369ac25ef41ab6bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999387"
---
# <a name="architecture-of-the-biztalk-esb-toolkit"></a>BizTalk ESB Toolkit のアーキテクチャ
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一連をサポートし、メッセージ ベースのエンタープライズ アプリケーションを構築しやすく疎結合メッセージング環境を実装するコンポーネントの相互運用で構成されています。 サービスとコンポーネントは、次の 7 つのカテゴリに自然な分類されます。  
  
- **Web サービス。** スケジュール処理、例外管理、エンドポイント、マップ、BizTalk Server の処理、Universal Description, Discovery, and Integration (UDDI) の相互運用性、およびメッセージ コンテンツの変換の解像度などの内部サービスを公開これら.  
  
- **スケジュール サービス。** これらには、変換、およびメッセージのルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます。 スケジュール処理では、参加しているカスタムのサービスを作成できます。 これらには、変換、およびメッセージのルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます。 スケジュール処理では、参加しているカスタムのサービスを作成できます。  
  
- **スケジュール オンランプします。** これら外部メッセージを受信、メッセージごとに適切なスケジュールをアタッチおよびスケジュールの処理を実行使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。  
  
- **傾斜します。** スケジュール オンランプとは異なりは、外部メッセージを受信これらの形式と HTTP、Java Message Service (JMS)、IBM WebSphere MQ (WMQ)、ファイル転送プロトコル (FTP)、フラット ファイル、および XML などのトランスポートの範囲内です。 一般的な BizTalk Server は必要に応じて使用する受信場所、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。  
  
- **オフランプします。** これらの実装では、形式と WCF、JMS、WMQ、FTP、HTTP、フラット ファイル、XML、またはその他のすべてのカスタム形式などのトランスポートを使用してメッセージの配信用のポートを送信します。 一般的な BizTalk Server が直接バインドされる動的送信ポートとメッセージ ボックスに、必要に応じて使用される、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのエンドポイントの動的解決のためのプロバイダー フレームワークとメタデータ。  
  
- **例外管理フレームワーク。** これには、例外 Web サービスでは、例外管理 API、および強化、処理、および例外の詳細を渡す ESB 管理ポータルにコンポーネントが含まれます。  
  
- **ESB 管理ポータル。** このサンプル アプリケーションでは、レジストリのプロビジョニング、例外の仲介、アラート通知、および分析を提供します。  
  
  これらのコンポーネントとサービスの多くは、オーケストレーション、変換、およびビジネス ルール エンジンと、メッセージ ボックス データベースなど、BizTalk Server によって実装される機能に依存します。 図 1 は、カテゴリ、コンポーネント、および各カテゴリ内で発生する通常のサービスの概略を示していますで使用される、中核となる BizTalk Server のシステム コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
  ![ESB アーキテクチャ](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")  
  
  **図 1**  
  
  **アーキテクチャとのコンポーネント、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB Toolkit の動作  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージを受け取り、演算を実行して、おそらく (が常にではありません)、ルーティング、またはその他のカスタム変換などのプロセスを実行するには、プロセスが定義されています。 演算を指定するために必要な処理のコア コンポーネントが各メッセージに回覧用紙が関連付けられている手順を含むまたはメタデータを適用するプロセスを定義して、メッセージの内容を実行するタスクを必要とします。 これらの回覧用紙スケジュールと呼びますと自動的に解決、中央のリポジトリから取得およびできます入り口が受信すると、メッセージに添付します。  
  
 このルーティング スリップ アプローチでは、つまり、ESB メッセージごとに、特定の処理に関する予備知識が必要ないこと、サービス間の疎結合を提供します。 可能なさまざまなプロセスの概要と各プロセスを適用する方法を知るだけがあります。 使用可能なプロセスおよびプロセスと指示のマッピングをメッセージ内に指定するための広範囲なオプションが用意されているので、コードの変更やコンポーネントの再展開を必要とせずに動作を構成および調整するための柔軟なメカニズムが実現されています。  
  
## <a name="design-patterns"></a>設計パターン  
 プロセスがメッセージ ボックス データベースにメッセージを格納およびサブスクライバーを取得して、メッセージの処理命令に基づく、ESB を使用するアーキテクチャは、実質的に、ステート マシンの設計パターンを実装します。 さらに、ESB を実装し、一連のコア Web サービスを通じて、外部アプリケーションを含め、サービス指向方法では、コア機能を公開します。  
  
 BizTalk Server を設計する方法を疎結合これと[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]-ベースのアプリケーションの柔軟性の高いソリューションの生成し、業界で受け入れられているベスト プラクティスとなっています。