---
title: サンプル アーキテクチャ:ファイル アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- File adapters, security
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- File adapters, architecture examples
ms.assetid: fdcbba0c-e301-46ce-8940-d617232cafbd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 961c4e3f7820f88c4935e070c739aacaab5d1a63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271154"
---
# <a name="sample-architecture-file-adapter"></a>サンプル アーキテクチャ:ファイル アダプター
このトピックでは、ファイル アダプターを使用してメッセージを送受信するときに、サンプル アーキテクチャについて説明します。  
  
## <a name="file-adapter-components"></a>ファイル アダプタ コンポーネント  
 次の図は、ファイル アダプターを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。  
  
> [!NOTE]
>  このサンプルのアーキテクチャは、EDI アダプタを使用する場合にも適用できます。  
  
 **ファイル アダプタを示す図 1 サンプル アーキテクチャ**  
  
 ![サンプル ファイル アダプターのアーキテクチャ](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
 このサンプル アーキテクチャには、次のセクションで説明されているコンポーネントが含まれています。  
  
## <a name="perimeter-network-internet"></a>境界ネットワーク-インターネット  
 企業は、イントラネット ベースの通信では、ファイル プロトコルを使用する一般的と、このシナリオをサポートするためにインターネット境界ネットワーク内のサーバーでそのため必要がありません。  
  
## <a name="perimeter-network-intranet"></a>境界ネットワーク-イントラネット  
 ファイル サーバーがファイル アダプターを使用すると、イントラネット境界ネットワークであります。 これは、場所、パートナーは、メッセージをドロップされ、BizTalk ファイル受信アダプターがメッセージ取得このサーバーからサーバーです。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理、ファイル アダプター、および追跡ホスト)。** このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。 これは、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリが存在する受信、ルーティング、処理、およびメッセージを送信します。 このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。 さらに、このホストは、ファイルの送信を実行するホストのインスタンスが含まれ、受信アダプター。  
  
    > [!NOTE]
    >  パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。 高可用性のための BizTalk Server を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **SQL Server。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **ドメイン コント ローラー。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)