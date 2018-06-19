---
title: 'サンプル アーキテクチャ: ファイル アダプターの |Microsoft ドキュメント'
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
ms.openlocfilehash: 11884786f743ece21a8009ea339a251b107420c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269610"
---
# <a name="sample-architecture-file-adapter"></a>ファイル アダプターのサンプル アーキテクチャ:
このトピックでは、ファイル アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。  
  
## <a name="file-adapter-components"></a>ファイル アダプタ コンポーネント  
 次の図は、ファイル アダプタを使用する場合の BizTalk サンプル アーキテクチャのコンポーネントを示しています。  
  
> [!NOTE]
>  このサンプル アーキテクチャは、EDI アダプタを使用する場合にも適用できます。  
  
 **ファイル アダプタを示すサンプル アーキテクチャを図 1**  
  
 ![サンプル ファイル アダプターのアーキテクチャ](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
 このサンプル アーキテクチャには、次のセクションで説明されているコンポーネントが含まれています。  
  
## <a name="perimeter-network-internet"></a>境界ネットワーク-インターネット  
 企業ではイントラネット ベースの通信にファイル プロトコルを使用することが多いので、このシナリオをサポートするためにインターネットの境界ネットワーク内にサーバーを配置する必要はありません。  
  
## <a name="perimeter-network-intranet"></a>境界ネットワーク-イントラネット  
 ファイル アダプタを使用する場合、イントラネットの境界ネットワーク内にファイル サーバーがあります。 これはパートナーがメッセージをドロップするサーバーです。BizTalk ファイル受信アダプタはこのサーバーからメッセージを取得します。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理、ファイル アダプター、および追跡ホスト)。** このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。 ここには、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリがメッセージを受信、ルーティング、処理、および送信するために配置されています。 このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。 さらに、このホストには、ファイル送信アダプタとファイル受信アダプタを実行するホストのインスタンスが含まれています。  
  
    > [!NOTE]
    >  パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。 BizTalk Server の高可用性を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **SQL Server。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **ドメイン コント ローラー。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)