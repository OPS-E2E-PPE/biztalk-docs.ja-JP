---
title: "BizTalk Adapter 用 Oracle Database のアーキテクチャの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter, and WCF
- architecture of the Oracle Database adapter
- ODAC
- Oracle Data Access Components
- endpoint
- adapter, architecture
- endpoint address
- ODP.NET
- Oracle Data Provider for .NET
- architecture
ms.assetid: cc59beb5-327a-4b00-a45c-82cc9d505167
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f5d4a23b9802c04af37716f8bef07735d8f80bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-database"></a>BizTalk Adapter 用 Oracle Database のアーキテクチャの概要
アーキテクチャについて説明、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。 

理解、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アーキテクチャに役立ちます。  
  
-   関係を理解、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]と[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。  
  
-   セキュリティ境界を理解してよりソリューションでデータを保護することができます。  
  
-   理解、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]プロパティをバインドします。  
  
-   インストールに関する問題のトラブルシューティングを行います。  
  
このトピックを使用するエンド ツー エンド ソリューションのアーキテクチャについて説明、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースを操作するためにも、内部のアーキテクチャを記述し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
 
## <a name="adapter-architecture-overview"></a>アダプターのアーキテクチャの概要
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 このバインディングには、Oracle データベースとの通信を有効にする単一のカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]によってラップされた、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] 、ランタイムは経由でアプリケーションに公開されると、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の Oracle データ アクセス コンポーネント (ODAC) for Windows に含まれる .NET (ODP.NET) と、Oracle クライアントは、Oracle データ プロバイダーを使用して Oracle データベースと通信します。  
  
 次の図を使用して開発されたソリューションをエンド ツー エンド アーキテクチャを示しています、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 ![Oracle データベース アダプタ アーキテクチャ ダイアグラム](../../adapters-and-accelerators/adapter-oracle-database/media/bts-oracledb-architecturec.gif "bts_OracleDB_Architecturec")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]として Oracle データベースの公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 操作を実行し、Oracle データベースでデータへのアクセス、クライアント アプリケーションが SOAP メッセージを交換、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 前の図に 4 つの方法を示しています、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]消費されることができます。 これらは次のとおりです。  
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル アプリケーションです。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して Oracle データベースでの操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 ソリューションの開発の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデルをチャネルは、「 [WCF チャネル モデルを使用して Oracle データベースの開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)です。  
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル アプリケーション サービスを提供します。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Oracle データベースで操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されるメタデータから、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 詳細については、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルと[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[開発 Oracle データベースを使用してアプリケーションの WCF サービス モデル](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)です。  
  
-   BizTalk 受信場所または Microsoft BizTalk Wcf-custom アダプターを使用して構成されているポートを送信します。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能です。 WCF カスタム アダプターを使用して選択し、Oracle DB のバインドと、受信場所の動作を構成したり、送信ポートできます。 使用する方法についての詳細、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[、BizTalk アプリケーションの開発](../../core/develop-your-biztalk-applications.md)です。  
  
-   IIS でホストされる Web サービスを介して。 このシナリオでは、アダプターを使用して生成された WCF サービス プロキシは標準の WCF Http バインドを使用して IIS でホストされます。 これは、外部のユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、自動的に実行時に、さらに、Oracle データベースと通信するアダプターをホストします。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODAC が常にホストされていると、アプリケーションまたはサービス アダプターを使用するとインプロセスでします。  
  
## <a name="oracle-database-adapter-and-wcf"></a>Oracle データベース アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントとサービス間のチャネル上で SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
-   *エンドポイント アドレス*メッセージが受信場所を指定します。  
  
-   A*バインディング*、メッセージ交換に使用する通信プロトコルを指定します。  
  
-   A*コントラクト*、エンドポイントによって公開される操作とデータ型を指定します。  
  
 バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくとも、バインディングはトランスポートとエンドポイントにメッセージを交換するために使用されるエンコーディングを指定します。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングのバインド要素の 1 つの具象実装です。 [WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデルです。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]カスタムのバインディングでは、Oracle DB バインド (**Microsoft.Adapters.OracleDB.OracleDBBinding**)。 既定では、このバインディングに 1 つのカスタム トランスポート バインド要素、Oracle データベース アダプターのバインド要素が含まれています (**Microsoft.Adapters.OracleDB.OracleDBAdapter**)、Oracle データベースでの操作を有効にします。  
  
 **Microsoft.Adapters.OracleDB.OracleDBBinding** (、Oracle DB バインディング) および**Microsoft.Adapters.OracleDB.OracleDBAdapter** (Oracle データベース アダプターのバインド要素) のパブリック クラスに公開されても、構成システムです。 Oracle データベース アダプターのバインド要素がパブリックに公開されているため、独自のカスタムをビルドすることができます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインディングの機能を拡張するための対応、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 たとえばでエンタープライズ シングル サインオン (SSO) をサポートするカスタム バインディングを実装する可能性があります、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービス モデルのソリューションです。 これを行うための理由は、1 つの多機能オペレーションまたはカスタム アプリケーションによって実装される操作と Oracle データベースでの操作の間でのスキーマの変換を実行する集計のデータベース操作になります。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の上に構築された、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用してユーザーとアダプターのクライアントに各種の機能を提供します。  

## <a name="oracle-database-adapter-and-wcf-lob-adapter-sdk"></a>Oracle データベース アダプターと WCF LOB Adapter SDK
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]によって提供される機能を活用するコア コンポーネントのセットが実装されて、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]し Oracle データ プロバイダーを使用して Oracle データベースへの接続に for .NET (ODP.NET) を指定します。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、ソフトウェアのレイヤーの役割を果たす、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]インターフェイスを持つ、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。 ODP.NET が使用されるレイヤーとして機能、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースがあるインターフェイスです。 
 
次の図の内部コンポーネント間の関係を示しています、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ODP.NET とします。  
  
 ![Oracle データベース アダプターの内部アーキテクチャ](../../adapters-and-accelerators/adapter-oracle-database/media/fa730561-9db7-40d1-bfcd-bc4eb119eea8.gif "fa730561-9db7-40d1-bfcd-bc4eb119eea8")  
 
   
## <a name="odpnet"></a>ODP.NET  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET、Oracle クライアントを使用して Oracle データベースを使用して接続します。 これらのコンポーネントは、Oracle データ アクセス コンポーネント (ODAC) の一部です。  
  
 ODP.NET では、ADO.NET インターフェイスと整合性が Oracle データベースのデータ プロバイダーを実装します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET によって公開されるクラスを使用して、Oracle データベースに対して実行します。  
  
 Oracle クライアントは、Oracle データベースへの接続を提供します。 接続 URI を提供することにより、Oracle データベースへの接続を確立する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 2 つの方法では、接続 URI を指定できます。  
  
-   **Tnsnames.ora を使用して**です。 この方法では、アダプター クライアントによって提供される URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、net サービス名のエントリ、ファイルからサーバー名、サービス名、ポート番号などの接続パラメーターを抽出します。 このアプローチを使用するのには、tnsnames.ora ファイルに、Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成しなければなりません。  
  
-   **Tnsnames.ora を使用せず**です。 この方法では、アダプターのクライアントは、接続 URI の直接接続パラメーターを指定します。 これは、操作では、tnsnames.ora ファイル、クライアント コンピューター上に存在する net サービス名は必要ありません。 クライアント コンピューターに存在している tnsnames.ora ファイルが、この方法でもは必要はありません。  
  
 接続 URI の詳細については、次を参照してください。 [Oracle データベースへの接続を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)です。
  
## <a name="next"></a>Next
[Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)