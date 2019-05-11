---
title: BizTalk Adapter for Oracle E-business Suite のアーキテクチャの概要 |Microsoft Docs
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
ms.openlocfilehash: e5360a26fc0df13548b7c0e6b26e5a59cb5eba50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375798"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-e-business-suite"></a>BizTalk Adapter for Oracle E-business Suite のアーキテクチャの概要
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 このバインディングには、Oracle E-business Suite との通信を有効にする 1 つのカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]によってラップされて、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]ランタイムを使ってアプリケーションに公開されると、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET (ODP.NET) と、Oracle クライアントでは、Windows の Oracle Data Access Components (ODAC) の一部であるは、Oracle データ プロバイダーを介して、Oracle E-business Suite と通信します。  
  
 次の図は、エンド ツー エンドのアーキテクチャを使用して開発されたソリューションを[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
 ![Oracle データベース アダプタ アーキテクチャ ダイアグラム](../../adapters-and-accelerators/adapter-oracle-ebs/media/967bc4a5-852b-479e-8ef0-941773f5991f.gif "967bc4a5-852b-479e-8ef0-941773f5991f")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]として Oracle E-business Suite を公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 クライアント アプリケーションが SOAP メッセージを交換する操作を実行し、Oracle E-business Suite でのデータへのアクセスを[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 前の図を 4 つの方法を示しています、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]消費されることができます。 これらは次のとおりです。   
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーション。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して、Oracle E-business Suite での操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーション。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Oracle E-business suite 操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されているメタデータから、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
- BizTalk 受信場所または送信ポートを Microsoft BizTalk Wcf-custom アダプターを使用するように構成します。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能。 Wcf-custom アダプターを使用して選択し、Oracle EBS のバインドと、受信場所の動作を構成または送信ポートすることができます。 使用する方法についての詳細、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[Oracle E-business Suite アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)します。  
  
- IIS でホストされる Web サービスを介して。 このシナリオでアダプターを使用して生成された WCF サービスのプロキシは、basicHttpBinding の WCF バインドを使用して、IIS でホストされます。 これは、外部ユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、さらに、通信して、Oracle E-business Suite を使用する実行時にアダプターを自動的にホストします。  
  
  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODAC が常にホストされていると同じプロセスで、アプリケーションまたはアダプターを使用するサービス。  
  
## <a name="oracle-ebs-adapter-and-wcf"></a>Oracle EBS アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] クライアントとサービス間のチャネル上での SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
- *エンドポイント アドレス*メッセージを受信場所を指定します。  
  
- A*バインド*メッセージを交換するために使用する通信プロトコルを指定します。  
  
- A*コントラクト*、エンドポイントによって公開される操作とデータ型を指定します。  
  
  バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくともバインドは、トランスポートとエンコーディング エンドポイントとメッセージ交換に使用されるを指定する必要があります。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングでバインド要素の 1 つの具象実装です。 [WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデル。  
  
  [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公開、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Oracle E-business Suite のバインド、カスタム バインディング (**Microsoft.Adapters.OracleEBS.OracleEBSBinding**)。 このバインディングには既定には、Oracle E-business Suite アダプターのバインド要素の 1 つのカスタム トランスポート バインド要素が含まれています (**Microsoft.Adapters.OracleEBS.OracleEBSAdapter**)、Oracle に対する操作を有効にします。E-business Suite。  
  
  **Microsoft.Adapters.OracleEBS.OracleEBSBinding** (、Oracle E-business Suite バインド) と**Microsoft.Adapters.OracleEBS.OracleEBSAdapter** (Oracle E-business Suite アダプターのバインド要素) は、パブリッククラスとは、構成システムにも公開します。 Oracle E-business Suite アダプターのバインド要素は一般に公開されるため、独自のカスタムを構築できます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドの機能を拡張できる、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 たとえば、エンタープライズ シングル サインオン (SSO) をサポートするカスタム バインドを実装するで、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービスのモデル ソリューション。 これを行う理由は、1 つの多機能オペレーションまたはカスタム アプリケーションによって実装される操作と Oracle E-business suite 操作の間のスキーマの変換を実行する集計のデータベース操作になります。  

## <a name="oracle-ebs-adapter-and-the-wcf-lob-sdk"></a>Oracle EBS アダプターと WCF LOB SDK
 
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の上に構築、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。 


[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供します、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用してユーザーとアダプター クライアントに豊富な機能を提供します。  使用するソフトウェア レイヤーとしても機能、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]とのインターフェイス、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。 ODP.NET が使用されるレイヤーとして機能、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースとのインターフェイス。 

次の図の内部コンポーネント間の関係を示しています、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ODP.NET と。  
  
 ![Oracle E&#45;ビジネス アダプターの内部アーキテクチャ](../../adapters-and-accelerators/adapter-oracle-ebs/media/bts-oracleebs-architecture-internalc.gif "bts_OracleEBS_Architecture_Internalc")  
  
## <a name="odpnet"></a>ODP.NET  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET、Oracle クライアントを通じて、Oracle E-business Suite に接続します。 これらのコンポーネントは、Oracle Data Access Components (ODAC) の一部です。  
  
 ODP.NET では、ADO.NET インターフェイスと整合性がある Oracle E-business Suite 用のデータ プロバイダーを実装します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET によって公開されるクラスを使用して、Oracle E-business suite 操作します。  
  
 Oracle クライアントでは、Oracle E-business Suite への接続を提供します。 接続 URI を提供することで、Oracle E-business Suite への接続を確立する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 2 つの方法では、接続 URI を指定できます。  
  
- **Tnsnames.ora を使用して**します。 この方法では、アダプター クライアントによって提供された URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。 アダプターは、ファイルの net サービス名のエントリから、サーバー名、サービス名、ポート番号などの接続パラメーターを抽出します。 このアプローチを使用するには、tnsnames.ora ファイルで Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成する必要があります。  
  
- **Tnsnames.ora を使用せず**します。 この方法では、アダプターのクライアントは、直接接続 URI の接続パラメーターを指定します。 これは、クライアント コンピューターの tnsnames.ora ファイルに存在する net サービス名には必要ありません。 この方法は、クライアント コンピューターに存在している、tnsnames.ora ファイルをも必要ありません。  
  
  接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)します。  
  
## <a name="next"></a>Next
[Oracle EBS アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)