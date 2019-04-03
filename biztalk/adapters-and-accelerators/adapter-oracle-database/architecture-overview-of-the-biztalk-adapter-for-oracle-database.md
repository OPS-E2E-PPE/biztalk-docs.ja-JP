---
title: BizTalk Adapter for Oracle Database のアーキテクチャの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6024bc9dedc1ea4b28e185bbc6ed8a025d9e71fd
ms.sourcegitcommit: af438e8cf6f58e25372689c5de0a184a0a6696a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58867572"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-database"></a>BizTalk Adapter for Oracle Database のアーキテクチャの概要
アーキテクチャについて説明します、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。 

理解、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アーキテクチャに役立ちます。  
  
- 間の関係を理解、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。  
  
- セキュリティの境界を理解して向上ソリューションでデータを保護することができます。  
  
- 理解、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]プロパティをバインドします。  
  
- インストールに関する問題のトラブルシューティングを行います。  
  
このトピックでは、使用するエンド ツー エンド ソリューションのアーキテクチャを説明します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースを操作する内部のアーキテクチャについても説明し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
 
## <a name="adapter-architecture-overview"></a>アダプターのアーキテクチャの概要
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 このバインディングには、Oracle データベースと通信する 1 つのカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]によってラップされて、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] 、ランタイムによってアプリケーションに公開されると、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] .NET (ODP.NET) と、Oracle クライアントでは、Windows の Oracle Data Access Components (ODAC) の一部であるは、Oracle Data Provider を使用して Oracle データベースと通信します。  
  
 次の図は、エンド ツー エンドのアーキテクチャを使用して開発されたソリューションを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
 ![Oracle データベース アダプタ アーキテクチャ ダイアグラム](../../adapters-and-accelerators/adapter-oracle-database/media/bts-oracledb-architecturec.gif "bts_OracleDB_Architecturec")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]として Oracle データベースの公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 クライアント アプリケーションが SOAP メッセージを交換する操作を実行し、Oracle データベースでのデータへのアクセスを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 前の図を 4 つの方法を示しています、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]消費されることができます。 これらは次のとおりです。  
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーション。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して Oracle データベースでの操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 ソリューションの開発の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルを参照してください[WCF チャネル モデルを使用して Oracle データベースの開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)します。  
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーション。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Oracle データベースで操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されているメタデータから、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 詳細については、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルと[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[開発 Oracle データベース アプリケーションの WCF サービス モデルを使用して](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)します。  
  
- BizTalk 受信場所または送信ポートを Microsoft BizTalk Wcf-custom アダプターを使用するように構成します。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能。 Wcf-custom アダプターを使用して選択し、Oracle DB のバインドと、受信場所の動作を構成または送信ポートすることができます。 使用する方法についての詳細、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[、BizTalk アプリケーションの開発](../../core/develop-your-biztalk-applications.md)します。  
  
- IIS でホストされる Web サービスを介して。 このシナリオでアダプターを使用して生成された WCF サービスのプロキシは、標準の WCF Http バインドを使用して、IIS でホストされます。 これは、外部ユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、さらに、Oracle データベースと通信する、実行時にアダプターを自動的にホストします。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODAC が常にホストされていると同じプロセスで、アプリケーションまたはアダプターを使用するサービス。  
  
## <a name="oracle-database-adapter-and-wcf"></a>Oracle Database アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] クライアントとサービス間のチャネル上での SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
- *エンドポイント アドレス*メッセージを受信場所を指定します。  
  
- A*バインド*メッセージを交換するために使用する通信プロトコルを指定します。  
  
- A*コントラクト*、エンドポイントによって公開される操作とデータ型を指定します。  
  
  バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくともバインドは、トランスポートとエンコーディング エンドポイントとメッセージ交換に使用されるを指定する必要があります。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングでバインド要素の 1 つの具象実装です。 [WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデル。  
  
  [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公開、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Oracle DB のバインド、カスタム バインディング (**Microsoft.Adapters.OracleDB.OracleDBBinding**)。 このバインディングには既定では、Oracle DB アダプターのバインド要素の 1 つのカスタム トランスポート バインド要素が含まれています (**Microsoft.Adapters.OracleDB.OracleDBAdapter**)、Oracle データベースで操作できます。  
  
  **Microsoft.Adapters.OracleDB.OracleDBBinding** (、Oracle DB のバインド) と**Microsoft.Adapters.OracleDB.OracleDBAdapter** (Oracle DB アダプターのバインド要素) のパブリック クラスに公開されても、構成システム。 独自のカスタムをビルドするには Oracle DB アダプターのバインド要素がパブリックに公開されている、ため[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドの機能を拡張できる、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 たとえば、エンタープライズ シングル サインオン (SSO) をサポートするカスタム バインドを実装するで、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービスのモデル ソリューション。 これを行う理由は、1 つの多機能オペレーションまたはカスタム アプリケーションによって実装される操作と Oracle データベースでの操作の間のスキーマの変換を実行する集計のデータベース操作になります。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の上に構築、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供します、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用してユーザーとアダプター クライアントに豊富な機能を提供します。  

## <a name="oracle-database-adapter-and-wcf-lob-adapter-sdk"></a>Oracle データベース アダプターと WCF LOB Adapter SDK
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]によって提供される機能を利用するコア コンポーネントのセットを実装、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] for .NET (ODP.NET) に Oracle Data Provider を使用して Oracle データベースへの接続を提供します。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]するソフトウェア レイヤーとして機能、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]とのインターフェイス、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。 ODP.NET が使用されるレイヤーとして機能、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースとのインターフェイス。 
 
次の図の内部コンポーネント間の関係を示しています、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ODP.NET とします。  
  
 ![Oracle データベース アダプターの内部アーキテクチャ](../../adapters-and-accelerators/adapter-oracle-database/media/fa730561-9db7-40d1-bfcd-bc4eb119eea8.gif "fa730561-9db7-40d1-bfcd-bc4eb119eea8")  
 
   
## <a name="odpnet"></a>ODP.NET  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET、Oracle クライアントを使用して Oracle データベースに接続します。 これらのコンポーネントは、Oracle Data Access Components (ODAC) の一部です。  
  
 ODP.NET は、ADO.NET インターフェイスと整合性がある Oracle データベースのデータ プロバイダーを実装します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ODP.NET によって公開されるクラスを使用して、Oracle データベースに対して機能します。  
  
 Oracle クライアントでは、Oracle データベースへの接続を提供します。 接続 URI を提供することで、Oracle データベースへの接続を確立する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 2 つの方法では、接続 URI を指定できます。  
  
- **Tnsnames.ora を使用して**します。 この方法では、アダプター クライアントによって提供された URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、ファイルの net サービス名のエントリから、サーバー名、サービス名、ポート番号などの接続パラメーターを抽出します。 このアプローチを使用するには、tnsnames.ora ファイルで Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成する必要があります。  
  
- **Tnsnames.ora を使用せず**します。 この方法では、アダプターのクライアントは、直接接続 URI の接続パラメーターを指定します。 これは、クライアント コンピューターの tnsnames.ora ファイルに存在する net サービス名には必要ありません。 この方法は、クライアント コンピューターに存在している、tnsnames.ora ファイルをも必要ありません。  
  
  接続 URI の詳細については、次を参照してください。 [Oracle データベースへの接続を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)します。
  
## <a name="next"></a>Next
[Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)
