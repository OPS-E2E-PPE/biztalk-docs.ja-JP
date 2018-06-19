---
title: 'サンプル アーキテクチャ: FTP アダプター |Microsoft ドキュメント'
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
ms.openlocfilehash: bed15e06027bec5e73c19cf73548674bc51ce68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269850"
---
# <a name="sample-architecture-ftp-adapter"></a>FTP アダプターのサンプル アーキテクチャ:
このトピックでは、FTP アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。  
  
 次の図は、FTP アダプタを使用する場合の BizTalk サンプル アーキテクチャのコンポーネントを示しています。  
  
 **FTP アダプタを示すサンプル アーキテクチャを図 1**  
  
 ![FTP アダプターのアーキテクチャをサンプル](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
 このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれています。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク - インターネット  
 FTP アダプタを使用する場合、インターネットの境界ネットワーク内に FTP サーバーがあります。  
  
> [!NOTE]
>  環境の外部、FTP サーバーを配置することも — ネットワークでは、パートナーのまたはサード パーティの独立系ソフトウェア ベンダー (ISV) によってホストされています。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク - イントラネット  
 企業ではインターネット ベースの通信に FTP プロトコルを使用することが多いので、このシナリオをサポートするためにイントラネットの境界ネットワーク内にサーバーを配置する必要はありません。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理、FTP アダプター、および追跡ホスト)。** このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。 ここには、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリがメッセージを受信、ルーティング、処理、および送信するために配置されています。 このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。 さらに、FTP 送信アダプタと FTP 受信アダプタを実行するホストのインスタンスが含まれています。  
  
    > [!NOTE]
    >  パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。 BizTalk Server の高可用性を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **SQL Server。** 同じ、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **ドメイン コント ローラー。** 場合と同じように同じ、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)