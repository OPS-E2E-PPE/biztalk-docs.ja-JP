---
title: サンプル アーキテクチャ:BizTalk メッセージ キュー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- Message Queuing binary protocol
- architecture, examples
- security, examples
- security, architecture
- examples, architecture
- MSMQ adapters, security
- architecture, security
- MSMQ adapters, architecture examples
- servers, Windows Message Queuing
- Windows Message Queuing
- message queuing adapters
ms.assetid: a660c798-1c45-4759-a6c8-f11550683a31
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9424562425854dba532e0c1650c6c9070469be0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393951"
---
# <a name="sample-architecture-biztalk-message-queuing"></a>サンプル アーキテクチャ:BizTalk メッセージ キュー
このトピックでは、BizTalk メッセージ キュー アダプタを使用してメッセージを送受信するときに、サンプル アーキテクチャについて説明します。  
  
 次の図は、BizTalk メッセージ キュー アダプタを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。  
  
 **BizTalk メッセージ キュー アダプタを示す図 1 サンプル アーキテクチャ**  
  
 ![BizTalk メッセージ キューのアーキテクチャのサンプル](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれます。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク-インターネット  
 メッセージ キュー バイナリ プロトコルを使用して、インターネット経由で勧めできません。 メッセージ キュー トラフィックがファイアウォール 1 経由しないようにします。 インターネット経由でメッセージを受信する BizTalk メッセージ キュー アダプタを使用する場合は、次の操作を行います。  
  
-   境界ネットワーク内のメッセージ キュー サーバーを使用します。  
  
-   インターネット経由でメッセージ キュー HTTP プロトコルを使用します。  
  
-   メッセージ キュー サーバーからメッセージを取得し、バイナリ プロトコルを使用して、BizTalk メッセージ キュー アダプタに転送を境界ネットワークで転送アプリケーションがあります。  
  
    > [!IMPORTANT]
    >  インターネットからメッセージを受信 BizTalk メッセージ キューを使用する場合でも、ファイアウォール 1 で BizTalk メッセージ キューで使用する必要があります残っているポートが閉じられます。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク-イントラネット  
 イントラネットからメッセージを受信 BizTalk メッセージ キュー アダプタを使用すると、BizTalk メッセージ キュー アダプタのホスト インスタンスが実行されている BizTalk Server にメッセージ キュー トラフィックを転送する Windows メッセージ キュー サーバーがあります。  
  
 イントラネットおよび E ビジネス ドメインは、一般的な Active Directory を共有している場合は、適切な送信先 (BizTalk メッセージ キューのホスト インスタンスが実行されている BizTalk Server 受信アダプター) に達するまで、メッセージは一連のメッセージ キュー ルーターを通過します。 1 つ目の安全性が低いために、このオプションは、図で表されません。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理、BizTalk メッセージ キュー アダプタ、および追跡ホスト)。** このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。 これは、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリが存在する受信、ルーティング、処理、およびメッセージを送信します。 このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。 さらに、このホストには、BizTalk メッセージ キューの実行を送信し、受信アダプター、ホストのインスタンスが含まれています。  
  
    > [!NOTE]
    >  パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **SQL Server。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **ドメイン コント ローラー。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)