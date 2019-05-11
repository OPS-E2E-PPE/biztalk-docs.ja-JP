---
title: サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, background information
- service solutions, about service solutions
- service solution tutorial, about service solution tutorial
- Service Oriented Architecture (SOA)
ms.assetid: 56a2ad90-74bb-489a-ab1d-900f3bea3d64
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7114ab32084abd45eb6169e1bb4e54bcf3b5f25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292709"
---
# <a name="understanding-the-service-oriented-solution"></a>サービス指向ソリューション
サービス指向ソリューションは、サービスとして設計された預金残高を記録するアプリケーションです。 このアプリケーションは、サービスとして公開されている 3 つのバックエンド アプリケーションを使用して、預金残高の必要な情報を取得します。  
  
 サービス指向アーキテクチャ (SOA) は、分散システムの構築と部分的に重複するアプローチです。 サービス指向アプローチには、いくつかの特性があります。  
  
- 疎結合である。 このアプリケーションのビジネス ロジックは、サービスを処理するロジックと区別されています。  
  
- 検出可能である。 サービスを検出するアプリケーション用のメカニズムがあります。  
  
- コントラクトを使用する。 サービスに対するインターフェイスでは、ユーザーとサービス間のコントラクトを実装します。  
  
  文献では、多くの場合、サービス指向アプローチを Web サービスと同じように扱っています。ただし、必ずしも同義ではありません。 Web サービスは、サービス指向ソリューションを実装する有効な方法ですが、.NET リモート処理などの他の技術を使用しても、サービスを作成することはできます。  
  
  サービス指向アーキテクチャの詳細についてを参照してください「Service Interface」 [ http://go.microsoft.com/fwlink/?LinkId=46185 ](http://go.microsoft.com/fwlink/?LinkId=46185)とでの「Service-Oriented Integration」 [ http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)します。  
  
## <a name="reader-guidance"></a>対象読者  
 このソリューションのドキュメントに精通していることを前提としています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念に精通していることも前提とします。  
  
 さらに、開発者向けのマニュアルを読み、理解するためには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを構築する方法や、プロジェクトの作成、参照の設定、BizTalk ソリューションのデバッグおよびテストなどのタスクについても精通している必要があります。  
  
## <a name="credit-card-reporting-at-woodgrove-bank"></a>Woodgrove Bank のクレジット カード記録  
 このサービス指向アーキテクチャのソリューションは、クレジット カードの残高を記録する Woodgrove Bank のサービスです。 銀行は架空のシナリオではありません — シナリオが実際に展開された顧客アプリケーションに基づきます。  
  
 このシナリオでは、次の 2 つのソースからクレジット カード残高が要求されます。  
  
- 音声自動応答 (IVR) アプリケーション  
  
- Web ページやカスタム クライアント アプリケーションなどの対話形式のクライアント  
  
  このソリューションでは、IVR アプリケーションからの要求は MQSeries を介して受け取ります。 対話形式のクライアントからの要求は、HTTP および SOAP を使用する Web サービスを介して処理されます。  
  
  新しいサービス指向アーキテクチャのアプリケーションは、多くの場合、Web サービスを使用する Web サイトなどの新しいアプリケーションの機能と同様に、古い技術を使用しているレガシ アプリケーションとの連携が必要になります。 シナリオは、この現実世界の要件をモデル化、IVR アプリケーションが顧客サービスのクライアント アプリケーションの中に、従来のアプリケーションを表し、最新であります。  
  
  Woodgrove Bank アプリケーションは、3 つのバックエンド レガシ システムのデータを使用して、要求に応答します。  
  
- 全体のクレジット限度額を提供するアプリケーション。 このアプリケーションは、メインフレーム コンピュータの SAP システムです。  
  
- アカウントの未処理トランザクションの合計額を記録する Pending Transactions システム。 このシステムは、メインフレームまたは AS 400 システムです。 このソリューションは、Web サービスおよび Microsoft Host Integration Server (HIS) を使用して、メインフレームまたは AS/400 システムと通信します。  
  
- 最新の支払いをシステムに記録する Payment Tracking システム。 MQSeries を使用して、Payment Tracking システムにアクセスできます。  
  
  レガシ システムからの情報の収集および編集を行った後、このソリューションは、元のアプリケーション (つまり、顧客) に応答を返します。  
  
## <a name="business-requirements"></a>ビジネス要件  
 クレジット記録アプリケーションは、顧客の要求にリアルタイムで応答し、要求をすばやく処理するため、短い待機時間を設定する必要があります。 また、多くの同時要求にも対応する必要があります。 このソリューションでは機密情報とパブリック インターフェイスを使用するため、セキュリティが大きな課題です。 最後に、信頼性の高いサービスにする必要があります。  
  
 ソリューションがこれらの要件を満たす方法については、次を参照してください。[サービス指向ソリューションの開発](../core/developing-a-service-oriented-solution.md)します。  
  
## <a name="performance-characteristics"></a>パフォーマンスの特性  
 ビジネス要件を満たすには、次のパフォーマンス特性が、シナリオには。  
  
-   維持可能なスループットは 1 秒あたり 40 個の受信要求処理。  
  
-   最大スループットは 1 秒あたり 100 個の受信要求処理。  
  
-   BizTalk Server で送受信する要求の 90%を 1000 ミリ秒未満で処理。  
  
-   BizTalk Server で送受信する要求の 95%を 2000 ミリ秒未満で処理。  
  
-   BizTalk Server で送受信する要求の 100%を 5000 ミリ秒未満で処理。  
  
> [!NOTE]
>  これらの時間にバックエンド システムの待機時間は含まれません。  
  
## <a name="three-versions-of-the-solution"></a>ソリューションの 3 つのバージョン  
 このソリューションには 3 つのバージョンがあります。  
  
- スタブ バージョンは、すべてのバックエンド システムをソフトウェア スタブに置き換えます。 このスタブは、バックエンド システムをシミュレートします。 このバージョンは、1 台のコンピュータでこのソリューションの展開および実行をすばやく行います。  
  
- アダプタ バージョンは、BizTalk アダプタを使用して、バックエンド システムに接続します。 このバージョンは、最初に思いつくこのソリューションの実装方法です。 ただし、アダプタを使用してメッセージをバックエンド システムに送信すると、応答を返す待機時間が長くなります。 アダプタの待機時間自体は非常に短いのですが、BizTalk Server の分散アーキテクチャでは、アダプタがメッセージ ボックスを使用して、オーケストレーションのホスト インスタンスと通信する必要があります。 このため、データベースへのラウンド トリップが発生して、待機時間が影響を受けます。  
  
- インライン バージョンでは、バックエンド システムと直接通信するインライン コードにアダプタを置き換えます。 このソリューションのインライン バージョンは、最も短い待機時間で最も高いスループットを実現します。  
  
  この展開ガイドでは、Pending Transactions システムに HIS を使用して接続する各バージョンのシミュレート方法と、このソリューションの 3 つのすべてのバージョンを作成および展開する方法について説明します。 構築とソリューションのデプロイについては、次を参照してください。[サービス指向ソリューションを展開する](../core/deploying-the-service-oriented-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューション](../core/service-oriented-solution.md)