---
title: "BizTalk メッセージ キューのサンプル アーキテクチャ: |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f38d373680fd1b47722fc1ac52c56b113ef59cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-biztalk-message-queuing"></a>BizTalk メッセージ キューのサンプル アーキテクチャ:
ここでは、BizTalk メッセージ キュー アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。  
  
 次の図は、BizTalk メッセージ キュー アダプタを使用する場合の BizTalk Server サンプル アーキテクチャのコンポーネントを示しています。  
  
 **BizTalk メッセージ キュー アダプタを示すサンプル アーキテクチャを図 1**  
  
 ![サンプル アーキテクチャの BizTalk メッセージ キューの](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 このサンプル アーキテクチャには、次のセクションに記載されているコンポーネントが含まれています。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク - インターネット  
 インターネット経由でメッセージ キュー バイナリ プロトコルを使用することはお勧めしません。 メッセージ キュー トラフィックがファイアウォール 1 経由することはできません。 インターネット経由でメッセージを受信する BizTalk メッセージ キュー アダプタを使用する場合は、次の操作を行います。  
  
-   境界ネットワーク内でメッセージ キュー サーバーを使用します。  
  
-   インターネット経由でメッセージ キュー HTTP プロトコルを使用します。  
  
-   境界ネットワーク内に、メッセージ キュー サーバーからメッセージを取得し、バイナリ プロトコルを使用してそのメッセージを BizTalk メッセージ キュー アダプタに転送する転送アプリケーションを用意します。  
  
    > [!IMPORTANT]
    >  BizTalk メッセージ キューを使用してインターネットからメッセージを受信する場合でも、BizTalk メッセージ キューで使用するポートは、ファイアウォール 1 では閉じたままにしてください。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク - イントラネット  
 BizTalk メッセージ キュー アダプタを使用してイントラネットからメッセージを受信する場合、BizTalk メッセージ キュー アダプタのホスト インスタンスを実行する BizTalk Server にメッセージ キュー トラフィックを転送する Windows メッセージ キュー サーバーがあります。  
  
 イントラネットおよび E ビジネス ドメインで共通の Active Directory を共有する場合、メッセージは適切な送信先 (BizTalk メッセージ キューの受信アダプタのホスト インスタンスが実行されている BizTalk Server) に到達するまで、一連のメッセージ キュー ルーターを介して移動します。 このオプションは、最初のオプションよりセキュリティの強度が劣るため、この図では示していません。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理、BizTalk メッセージ キュー アダプター、および追跡ホスト)。** このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。 ここには、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリがメッセージを受信、ルーティング、処理、および送信するために配置されています。 このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。 さらに、このホストには、BizTalk メッセージ キューの送信アダプタと受信アダプタを実行するホストのインスタンスが含まれています。  
  
    > [!NOTE]
    >  パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **SQL Server。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **ドメイン コント ローラー。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)