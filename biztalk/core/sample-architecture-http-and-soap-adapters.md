---
title: "サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae8be185084a9a838876e3d50b605a63c161b66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-http-and-soap-adapters"></a>サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ
このトピックでは、HTTP アダプターと SOAP アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。  
  
 次の図は、HTTP アダプタまたは SOAP アダプタを使用する場合の BizTalk Server サンプル アーキテクチャのコンポーネントを示しています。  
  
 **HTTP アダプタまたは SOAP アダプタを示すサンプル アーキテクチャを図 1**  
  
 ![HTTP または SOAP アダプターのアーキテクチャをサンプル](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
 このサンプル アーキテクチャには、次のセクションに記載されているコンポーネントが含まれています。  
  
## <a name="perimeter-networkinternet"></a>境界ネットワーク - インターネット  
 リバース プロキシ ルール (、TMG サーバー実装が呼び出される Web 公開) を使用して、E ビジネスを保護するには、ファイアウォールに、インターネットに接続されたファイアウォール (ファイアウォール 1) からメッセージを中継することをお勧め、SOAP アダプターと HTTP アダプターを使用する場合ドメイン (ファイアウォール 2)、および BizTalk Server 分離ホストを実行するには、このファイアウォールからです。 Web 公開ルールの詳細については、Microsoft Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。  
  
> [!NOTE]
>  リバース プロキシを使用するときは、境界ネットワークに Web サーバーは必要ありません。  
  
## <a name="perimeter-networkintranet"></a>境界ネットワーク - イントラネット  
 企業では一般的にはインターネット ベースの通信に HTTP プロトコルと SOAP プロトコルを使用するので、このシナリオをサポートするためにイントラネット境界ネットワークにサーバーは必要ありません。 HTTP プロトコルまたは SOAP プロトコル経由で BizTalk Server と統合する内部アプリケーションがイントラネット内にある場合、インターネット境界ネットワークに対する推奨事項に従う必要があります。  
  
## <a name="e-business-domain"></a>E ビジネス ドメイン  
 このドメインには、BizTalk Server の実装によって使用されるインフラストラクチャとアプリケーションがすべて含まれます。 このドメイン内のサーバーは次のとおりです。  
  
-   **BizTalk Server (処理ホストおよび追跡ホスト)。** このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。 このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。  
  
    > [!NOTE]
    >  パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。  
  
-   **BizTalk Server (SOAP および HTTP アダプター用の分離ホスト)。** このサーバーには BizTalk Server ランタイムがインストールされていて、HTTP アダプタと SOAP アダプタを含むホストのインスタンスのみが含まれます。 HTTP アダプタと SOAP アダプタはそれぞれが実行されるコンピュータにインターネット インフォメーション サービス (IIS) をインストールする必要があるため、これらのホストは個別のサーバーで実行されます。  
  
    > [!NOTE]
    >  パフォーマンスを向上させる必要がある場合、HTTP アダプタ ホストと SOAP アダプタ ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。 これを行う場合、ネットワーク負荷分散 (NLB) を構成する必要もあります。 BizTalk Server の高可用性を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。  
  
-   **マスター シークレット サーバーです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **SQL Server。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **ドメイン コント ローラー。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
-   **管理ツールです。** 同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [脅威モデル分析のサンプル シナリオ](../core/sample-scenarios-for-threat-model-analysis.md)