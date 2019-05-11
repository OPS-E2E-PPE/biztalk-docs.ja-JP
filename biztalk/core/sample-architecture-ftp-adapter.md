---
title: サンプル アーキテクチャ:FTP アダプター |Microsoft Docs
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
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa9a9514d7e1524cd277e3e822f7b15a2904d7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393941"
---
# <a name="sample-architecture-ftp-adapter"></a>サンプル アーキテクチャ:FTP アダプター
このトピックでは、FTP アダプターを使用してメッセージを送信する場合、サンプル アーキテクチャについて説明します。  
  
 次の図は、FTP アダプターを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。  
  
 **FTP アダプタを示す図 1 サンプル アーキテクチャ**  
  
 ![FTP アダプターのアーキテクチャのサンプル](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
 このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれています。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク-インターネット  
 FTP サーバーが、FTP アダプターを使用すると、インターネット境界ネットワークであります。  
  
> [!NOTE]
>  環境の外部、FTP サーバーを配置することも、パートナーのネットワークに、またはサード パーティの独立系ソフトウェア ベンダー (ISV) によってホストされています。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク-イントラネット  
 企業は、インターネット ベースの通信に FTP プロトコルを使用する一般的と、このシナリオをサポートするためにイントラネット境界ネットワーク内のサーバーでそのため必要がありません。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理、FTP アダプター、および追跡ホスト)。** このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。 これは、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリが存在する受信、ルーティング、処理、およびメッセージを送信します。 このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。 さらに、このホストは、FTP 送信を実行するホストのインスタンスが含まれ、受信アダプター。  
  
    > [!NOTE]
    >  パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。 高可用性のための BizTalk Server を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **SQL Server。** 同じ、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **ドメイン コント ローラー。** 同じものと同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)