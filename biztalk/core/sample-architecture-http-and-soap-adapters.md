---
title: サンプル アーキテクチャ:HTTP アダプターと SOAP アダプター |Microsoft Docs
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
- SOAP adapters, security
- Web Publishing
- security, examples
- security, architecture
- SOAP adapters, architecture examples
- examples, architecture
- architecture, security
- HTTP adapters, architecture examples
- reverse proxy rules
- ISA Server implementation
- HTTP adapters, security
ms.assetid: 935197d0-5108-4970-b237-3c6d5b40c5e9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77b7d8557564cfa94bbfb243447e5e85d4b6865d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271074"
---
# <a name="sample-architecture-http-and-soap-adapters"></a>サンプル アーキテクチャ:HTTP アダプターと SOAP アダプター
このトピックでは、HTTP アダプタと SOAP アダプタを使用してメッセージを送受信するときに、サンプル アーキテクチャについて説明します。  
  
 次の図は、HTTP または SOAP アダプターを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。  
  
 **図 1. HTTP または SOAP アダプターを示すサンプル アーキテクチャ**  
  
 ![HTTP または SOAP アダプターのアーキテクチャのサンプル](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
 このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれます。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク-インターネット  
 リバース プロキシ ルールの (TMG サーバー実装は Web 公開呼びます) を使用して、E ビジネスを保護するファイアウォールからインターネットに接続されたファイアウォール (ファイアウォール 1) メッセージを中継することをお勧め、SOAP および HTTP アダプターを使用する場合ドメイン (ファイアウォール 2)、および BizTalk Server 分離ホストを実行するには、このファイアウォールから。 Web 公開ルールの詳細については、Microsoft Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=205340 ](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)します。  
  
> [!NOTE]
>  リバース プロキシを使用すると、境界ネットワーク内の Web サーバーは必要ありません。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク-イントラネット  
 企業はインターネット ベースの通信に HTTP および SOAP プロトコルを使用する一般的と、このシナリオをサポートするためにイントラネット境界ネットワーク内のサーバーでそのため必要がありません。 HTTP または SOAP プロトコルを通じて BizTalk Server と統合された、イントラネット内の内部アプリケーションがあれば、インターネット境界ネットワークの推奨事項に従ってください。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメインには、すべてのインフラストラクチャと、BizTalk Server の実装で使用するアプリケーションが含まれています。 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理ホストおよび追跡ホスト)。** このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。 このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。  
  
    > [!NOTE]
    >  パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。  
  
-   **BizTalk Server (SOAP および HTTP アダプター用の分離ホスト)。** このサーバーは、BizTalk Server ランタイムのインストールを備え、HTTP および SOAP アダプターが含まれているホストのインスタンスのみが存在します。 これらのホスト実行を別のサーバーでこれらのアダプターでは、コンピューターのインターネット インフォメーション サービス (IIS) をインストールする必要があるために実行されます。  
  
    > [!NOTE]
    >  パフォーマンス ニーズの増加に応じて、HTTP および SOAP アダプターのホストのホスト インスタンスの環境に BizTalk Server を追加できます。 これを行うときにネットワーク負荷分散 (NLB) を構成する必要もあります。 高可用性のための BizTalk Server を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **SQL Server。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **ドメイン コント ローラー。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)