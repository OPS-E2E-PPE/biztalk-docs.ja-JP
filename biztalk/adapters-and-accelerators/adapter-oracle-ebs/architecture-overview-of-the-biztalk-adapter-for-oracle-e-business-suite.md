---
title: BizTalk Adapter for Oracle E-business Suite のアーキテクチャの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f840ff23-4d68-4bd3-b115-aa87bc4c99f2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39c2353448a05747d94ae3128968182f428739ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216770"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-e-business-suite"></a>BizTalk Adapter for Oracle E-business Suite のアーキテクチャの概要
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 このバインディングには、Oracle E-business Suite での通信を有効にする単一のカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]によってラップされた、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]ランタイムは経由でアプリケーションに公開されると、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET (ODP.NET) と、Oracle クライアントを Windows の Oracle データ アクセス コンポーネント (ODAC) の一部である Oracle データ プロバイダーを通じて Oracle E-business Suite と通信します。  
  
 次の図に、使用して開発されたソリューションをエンド ツー エンド アーキテクチャ、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
 ![Oracle データベース アダプタ アーキテクチャ ダイアグラム](../../adapters-and-accelerators/adapter-oracle-ebs/media/967bc4a5-852b-479e-8ef0-941773f5991f.gif "967bc4a5-852b-479e-8ef0-941773f5991f")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]として Oracle E-business Suite の公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 操作を実行し、Oracle E-business Suite でのデータへのアクセス、クライアント アプリケーションが SOAP メッセージを交換、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 前の図に 4 つの方法を示しています、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]消費されることができます。 これらは次のとおりです。   
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル アプリケーションです。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して Oracle E-business Suite での操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル アプリケーション サービスを提供します。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Oracle E-business Suite での操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されるメタデータから、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
-   BizTalk 受信場所または Microsoft BizTalk Wcf-custom アダプターを使用して構成されているポートを送信します。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能です。 WCF カスタム アダプターを使用して選択し、Oracle EBS バインドと、受信場所の動作を構成したり、送信ポートできます。 使用する方法についての詳細、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[Oracle E-business Suite アダプターを使用して BizTalk の開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)です。  
  
-   IIS でホストされる Web サービスを介して。 このシナリオでは、アダプターを使用して生成された WCF サービス プロキシは basicHttpBinding WCF バインドを使用して、IIS でホストされます。 これは、外部のユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、自動的に実行時に、さらに、Oracle E-business Suite で通信するアダプターをホストします。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODAC が常にホストされていると、アプリケーションまたはサービス アダプターを使用するとインプロセスでします。  
  
## <a name="oracle-ebs-adapter-and-wcf"></a>Oracle EBS アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントとサービス間のチャネル上で SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
-   *エンドポイント アドレス*メッセージが受信場所を指定します。  
  
-   A*バインディング*、メッセージ交換に使用する通信プロトコルを指定します。  
  
-   A*コントラクト*、エンドポイントによって公開される操作とデータ型を指定します。  
  
 バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくとも、バインディングはトランスポートとエンドポイントにメッセージを交換するために使用されるエンコーディングを指定します。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングのバインド要素の 1 つの具象実装です。 [WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデルです。  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]カスタム バインドを Oracle E-business Suite バインド (**Microsoft.Adapters.OracleEBS.OracleEBSBinding**)。 既定では、このバインディングに 1 つのカスタム トランスポート バインド要素、Oracle E-business Suite アダプターのバインド要素が含まれています (**Microsoft.Adapters.OracleEBS.OracleEBSAdapter**)、Oracle での操作を有効にします。E-business Suite です。  
  
 **Microsoft.Adapters.OracleEBS.OracleEBSBinding** (、Oracle E-business Suite のバインド) と**Microsoft.Adapters.OracleEBS.OracleEBSAdapter** (Oracle E-business Suite アダプターのバインド要素) はパブリッククラスとは、構成システムに公開されています。 Oracle E-business Suite アダプターのバインド要素がパブリックに公開されているため、独自のカスタムをビルドすることができます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインディングの機能を拡張するための対応、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 たとえばでエンタープライズ シングル サインオン (SSO) をサポートするカスタム バインディングを実装する可能性があります、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービス モデルのソリューションです。 これを行うための理由は、1 つの多機能オペレーションまたはカスタム アプリケーションによって実装される操作と Oracle E-business Suite での操作の間でのスキーマの変換を実行する集計のデータベース操作になります。  

## <a name="oracle-ebs-adapter-and-the-wcf-lob-sdk"></a>Oracle EBS アダプターと WCF LOB SDK
 
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の上に構築された、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。 


[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用してユーザーとアダプターのクライアントに各種の機能を提供します。  使用するソフトウェア レイヤーとしても機能、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイスを持つ、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。 ODP.NET が使用されるレイヤーとして機能、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースがあるインターフェイスです。 

次の図の内部コンポーネント間の関係を示しています、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、および ODP.NET:  
  
 ![Oracle E &#45;ビジネス アダプターの内部アーキテクチャ](../../adapters-and-accelerators/adapter-oracle-ebs/media/bts-oracleebs-architecture-internalc.gif "bts_OracleEBS_Architecture_Internalc")  
  
## <a name="odpnet"></a>ODP.NET  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET および Oracle クライアントを通じて Oracle E-business Suite を使用して接続します。 これらのコンポーネントは、Oracle データ アクセス コンポーネント (ODAC) の一部です。  
  
 ODP.NET では、ADO.NET インターフェイスと整合性がある Oracle E-business Suite のデータ プロバイダーを実装します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET によって公開されるクラスを使用して Oracle E-business Suite で動作します。  
  
 Oracle クライアントは、Oracle E-business Suite への接続を提供します。 接続 URI を提供することによって Oracle E-business Suite への接続を確立する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 2 つの方法では、接続 URI を指定できます。  
  
-   **Tnsnames.ora を使用して**です。 この方法では、アダプター クライアントによって提供される URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、net サービス名のエントリ、ファイルからサーバー名、サービス名、ポート番号などの接続パラメーターを抽出します。 このアプローチを使用するのには、tnsnames.ora ファイルに、Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成しなければなりません。  
  
-   **Tnsnames.ora を使用せず**です。 この方法では、アダプターのクライアントは、接続 URI の直接接続パラメーターを指定します。 これは、操作では、tnsnames.ora ファイル、クライアント コンピューター上に存在する net サービス名は必要ありません。 クライアント コンピューターに存在している tnsnames.ora ファイルが、この方法でもは必要はありません。  
  
 接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)です。  
  
## <a name="next"></a>Next
[Oracle EBS アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)