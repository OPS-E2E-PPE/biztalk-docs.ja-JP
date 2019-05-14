---
title: BizTalk Adapter for mySAP Business Suite のアーキテクチャの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture of SAP adapter
- adapters, architecture
ms.assetid: 1b45edb0-2476-427b-b6cd-41e38ed815e0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81b556f9d91a896fc0a544cd78bfc043588a274b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374261"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite"></a>BizTalk Adapter for mySAP Business Suite のアーキテクチャの概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]実装、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドは、SAP システムと通信する 1 つのカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]によってラップされて、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]ランタイムを使ってアプリケーションに公開されると、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP Unicode RFC SDK (librfc32u.dll) の 64 ビットまたは 32 ビット バージョンのいずれかを使用して SAP システムと通信します。 

次の図は、エンド ツー エンドのアーキテクチャを使用して開発されたソリューションを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
 ![SAP エンド&#45;に&#45;アーキテクチャ終了](../../adapters-and-accelerators/adapter-sap/media/9ba0c31f-90df-444d-8192-42743c893d51.gif "9ba0c31f-90df-444d-8192-42743c893d51")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]としての SAP システムを公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 クライアント アプリケーションで SOAP メッセージを交換、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルの操作を実行して、SAP システムのデータにアクセスします。 上記の図を 4 つの方法を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]消費されることができます。  
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルを使用して SAP システムの操作を実行するアプリケーション、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 ソリューションの開発の詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用して[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのプログラミングは、「 [WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)します。  
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションでメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SAP システムの操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または作成する svcutil.exe ツールを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されているメタデータから、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのプログラミングと[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[WCF サービス モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)します。  
  
- Wcf-custom トランスポートの種類のバインドとして構成されている SAP バインドで、BizTalk WCF カスタム アダプターを使用するように構成された BizTalk ポートを介して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション。 BizTalk WCF カスタム アダプター間の通信を可能な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションと[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス。 BizTalk WCF カスタム アダプターは、カスタムをサポートしている[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]を介して WCF カスタム バインドのトランスポートの種類は、いずれかを構成することができます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドとして、BizTalk WCF カスタム アダプターで使用されるバインド構成システムに公開します。 使用する方法についての詳細、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)します。 BizTalk のトランザクションは、SAP バインドのバインド プロパティの設定を読み込むことができる BizTalk 階層チャネル バインド要素でサポートされます。  
  
- IIS でホストされる Web サービスを介して。 このシナリオで、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を介して公開される、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] 、標準のいずれかを使用して IIS でホストされているサービス プロキシ[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP バインドします。  
  
- を通じて、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]上で実行、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]し、SAP システムへの ADO.NET インターフェイスを提供します。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP RFC ライブラリが常にホストされていると同じプロセスで、アプリケーションまたはアダプターを使用するサービス。  
  
## <a name="sap-adapter-and-wcf"></a>SAP アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] クライアントとサービス間のチャネル上での SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。  
  
 エンドポイントから成る、*エンドポイント アドレス*、メッセージが受信される場所を指定する、*バインド*メッセージ、および、を交換するために使用する通信プロトコルを指定します。*コントラクト*エンドポイントによって公開される操作とデータ型を指定します。 バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。  
  
 少なくともバインディングはトランスポートとエンコーディング エンドポイントとメッセージを交換するために使用を指定する必要があります。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングでバインド要素の 1 つの具象実装です。  
  
[WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデル。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公開、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SAP バインド、カスタム バインディング (**Microsoft.Adapters.SAP.SAPBinding**)。 このバインディングには既定には、SAP アダプターのバインド要素の 1 つのカスタム トランスポート バインド要素が含まれています (**Microsoft.Adapters.SAP.SAPAdapter**)、SAP システムを操作できます。 使用する場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、設定することができます、 **EnableBizTalkCompatibilityMode**バインドのプロパティを BizTalk 層チャネル バインド要素、SAP アダプターのバインド上に、カスタム バインド要素を読み込む要素。 BizTalk 層チャネル バインド要素がによって内部的に実装されている、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP バインドの外部にさらされることはありません。  
  
 **Microsoft.Adapters.SAP.SAPBinding** (、SAP バインド) と**Microsoft.Adapters.SAP.SAPAdapter** (SAP アダプターのバインド要素) のパブリック クラスは、構成システムにも公開されます。 SAP アダプターのバインド要素は一般に公開されるため、独自のカスタムを構築できます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドの機能を拡張できる、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 たとえば、エンタープライズ シングル サインオン (SSO) でサポートするカスタム バインドを実装、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたは[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]service に 1 回の多機能操作または集計のデータベース操作に、モデルのプログラミング ソリューションカスタム アプリケーションによって実装される操作と SAP システムの操作の間のスキーマの変換を実行します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の上に構築、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供します、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]とアダプター クライアントのユーザーに豊富な機能を提供するを活用します。  

## <a name="sap-adapter-and-the-wcf-lob-adapter-sdk"></a>SAP アダプターと WCF LOB Adapter SDK
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]によって提供される機能を利用するコア コンポーネントのセットを実装、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] SAP Unicode RFC SDK ライブラリ (librfc32u.dll) を使用して SAP システムへの接続を提供します。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]するソフトウェア レイヤーとして機能、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と連動する[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]、RFC SDK が使用されるレイヤーとして機能し、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムとのインターフェイス。 次の図の内部コンポーネント間の関係を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]間、およびこれらのコンポーネントと、RFC SDK。  
  
 ![内部アダプター コンポーネントとの関係](../../adapters-and-accelerators/adapter-sap/media/10f97b95-4e82-4592-ba07-0f58478305c2.gif "10f97b95-4e82-4592-ba07-0f58478305c2")  
  
## <a name="connection-to-the-sap-system"></a>SAP システムへの接続  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP Unicode RFC SDK ライブラリ (librfc32u.dll) を使用して SAP システムに接続します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 32 ビットと 64 ビット バージョンの SAP RFC SDK の両方をサポートします。 SAP の RFC SDK では、SAP システムを ABAP 関数を呼び出す外部プログラムを使用できます。  
  
 接続 URI を提供することで、SAP システムへの接続を確立する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のような SAP システムへの接続をサポートしています。  
  
- アプリケーション ホスト ベース接続を (A) を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は SAP アプリケーション サーバーに直接接続します。  
  
- 負荷分散接続 (B) を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP メッセージ サーバーに接続します。  
  
- 変換先に基づく接続 (D) saprfc.ini ファイルの構成での変換先での SAP システムへの接続が指定されています。 A、B、および R タイプの接続がサポートされています。  
  
- Rfc、tRFC およびリスナーのホスト、リスナー ゲートウェイ サービスでは、リスナー プログラム ID、接続 URI で直接または R ベースのいずれかで指定されている SAP システムの RFC 転送先からの Idoc のアダプターが受信するリスナー接続 (R)saprfc.ini ファイルの構成で転送先。  
  
  Saprfc.ini ファイルの詳細については、"このを参照してください。INI ファイル"で、 [SAP ドキュメント](https://help.sap.com/doc/PRODUCTION/saphelp_nwpi711/7.1.1/en-US/48/c4168eca64581de10000000a42189c/frameset.htm)します。  
  
  方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続、SAP システムを参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)