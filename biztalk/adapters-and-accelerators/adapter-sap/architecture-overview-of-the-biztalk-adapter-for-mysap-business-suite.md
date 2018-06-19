---
title: BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要 |Microsoft ドキュメント
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
ms.openlocfilehash: d571cdd3beea2bc9a57ec7ad15f865e7ef51e53a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22218418"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite"></a>BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を実装する[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインディングは、SAP システムとの通信を有効にする単一のカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]によってラップされた、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]ランタイムは経由でアプリケーションに公開されると、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP Unicode RFC SDK (librfc32u.dll) の 64 ビットまたは 32 ビット バージョンのいずれかを使用して SAP システムと通信します。 

次の図を使用して開発されたソリューションをエンド ツー エンド アーキテクチャを示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
 ![SAP エンド&#45;に&#45;アーキテクチャを終了](../../adapters-and-accelerators/adapter-sap/media/9ba0c31f-90df-444d-8192-42743c893d51.gif "9ba0c31f-90df-444d-8192-42743c893d51")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]として SAP システムを公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 クライアント アプリケーションで SOAP メッセージを交換、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル操作を実行して、SAP システムでのデータにアクセスします。 上記の図に 4 つの方法を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]消費されることができます。  
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルを使用して SAP システムの操作を実行するアプリケーション、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 ソリューションの開発の詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用して[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのプログラミングは、「 [WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)です。  
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービスのメソッドを呼び出してモデル アプリケーション、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SAP システムでの操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または svcutil.exe ツールを作成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されるメタデータから、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 詳細については[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのプログラミングと[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[WCF サービス モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)です。  
  
-   Wcf-custom トランスポートの種類のバインドとして構成されている SAP バインドで、BizTalk WCF カスタム アダプターを使用するように構成する BizTalk ポートを介して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。 BizTalk WCF カスタム アダプターの間の通信を有効にする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションと[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス。 BizTalk WCF カスタム アダプターは、カスタム[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインディングを介してその Wcf-custom トランスポートの種類、いずれかを構成することにより[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]BizTalk Wcf-custom アダプターで使用するバインディングとして構成システムに公開するバインディング。 使用する方法についての詳細、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)です。 BizTalk トランザクションは、SAP バインドのバインドのプロパティを設定して読み込むことができます BizTalk 階層チャネルのバインド要素によってサポートされます。  
  
-   IIS でホストされる Web サービスを介して。 このシナリオでは、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]経由で公開されて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス プロキシは、標準のいずれかを使用して IIS でホストされる[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]HTTP バインドします。  
  
-   を介して、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]上で実行、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]し、SAP システムへの ADO.NET インターフェイスを提供します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP RFC ライブラリを常にホストとインプロセスでアプリケーションまたはサービス アダプターを使用するとします。  
  
## <a name="sap-adapter-and-wcf"></a>SAP アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] クライアントとサービス間のチャネル上で SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。  
  
 エンドポイントから成る、*エンドポイント アドレス*、メッセージが受信される場所を指定する、*バインディング*メッセージ、および、の交換に使用する通信プロトコルを指定します。*コントラクト*エンドポイントによって公開される操作とデータ型を指定します。 バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。  
  
 少なくとも、バインディングはトランスポートとエンドポイントとメッセージ交換に使用されるエンコーディングを指定します。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングのバインド要素の 1 つの具象実装です。  
  
[WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデルです。  
  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]カスタム バインドを SAP バインド (**Microsoft.Adapters.SAP.SAPBinding**)。 既定では、このバインディングに 1 つのカスタム トランスポート バインド要素、SAP アダプターのバインド要素が含まれています (**Microsoft.Adapters.SAP.SAPAdapter**)、SAP システムの操作を有効にします。 使用する場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、設定することができます、 **EnableBizTalkCompatibilityMode**バインディング プロパティを BizTalk 層チャネル バインド要素、SAP アダプターのバインド上に、カスタム バインド要素を読み込む要素。 BizTalk 層チャネル バインド要素がによって内部的に実装されている、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP バインドの外部にさらされることはありません。  
  
 **Microsoft.Adapters.SAP.SAPBinding** (、SAP バインド) と**Microsoft.Adapters.SAP.SAPAdapter** (SAP アダプターのバインド要素) のパブリック クラスは、構成システムにも公開されます。 独自のカスタムをビルドするには、SAP アダプターのバインド要素がパブリックに公開されているため[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインディングの機能を拡張するための対応、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 たとえば、エンタープライズ シングル サインオン (SSO) でサポートするためにカスタム バインディングを実装する可能性があります、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたは[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービスの 1 つの多機能オペレーション、または集計のデータベース操作に、モデルのプログラミング ソリューションスキーマのカスタム アプリケーションによって実装される操作および操作の SAP システムの間で変換を実行します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の上に構築された、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]活用してユーザーとアダプターのクライアントに豊富な一連の機能を提供します。  

## <a name="sap-adapter-and-the-wcf-lob-adapter-sdk"></a>SAP アダプターと WCF LOB Adapter SDK
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]によって提供される機能を活用するコア コンポーネントのセットが実装されて、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] SAP Unicode RFC SDK ライブラリ (librfc32u.dll) を使用して SAP システムへの接続を提供します。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、ソフトウェアのレイヤーの役割を果たす、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]インターフェイスを持つ[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]、RFC SDK が使用されるレイヤーとして機能し、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムを持つインターフェイスです。 次の図の内部コンポーネント間の関係を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]間およびこれらのコンポーネントと、RFC SDK。  
  
 ![内部アダプター コンポーネントとの関係](../../adapters-and-accelerators/adapter-sap/media/10f97b95-4e82-4592-ba07-0f58478305c2.gif "10f97b95-4e82-4592-ba07-0f58478305c2")  
  
## <a name="connection-to-the-sap-system"></a>SAP システムへの接続  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP Unicode RFC SDK ライブラリ (librfc32u.dll) を使用して SAP システムを使用して接続します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 32 ビットと 64 ビット バージョンの SAP RFC SDK の両方をサポートします。 SAP RFC SDK では、関数を呼び出す ABAP SAP システムで外部プログラムを使用できます。  
  
 接続 URI を提供することで、SAP システムへの接続を確立する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のような SAP システムへの接続をサポートしています。  
  
-   アプリケーション ホスト ベース接続 (A) を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP アプリケーション サーバーに直接接続します。  
  
-   負荷分散の接続 (B) を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP メッセージ サーバーに接続します。  
  
-   宛先に基づく接続 (D) saprfc.ini 構成ファイル内の変換先での SAP システムへの接続が指定されています。 A、B、および R タイプの接続はサポートされています。  
  
-   Rfc、tRFC およびリスナー ホスト、リスナー ゲートウェイ サービス、および接続 URI 内で直接、または R ベースで、リスナーのプログラム ID で指定されている SAP システムで、RFC 変換先での Idoc のアダプターが受信するリスナー接続 (R)saprfc.ini 構成ファイルのコピー先です。  
  
 Saprfc.ini ファイルの詳細については、"このを参照してください。INI ファイル」で、 [SAP のマニュアル](https://help.sap.com/doc/PRODUCTION/saphelp_nwpi711/7.1.1/en-US/48/c4168eca64581de10000000a42189c/frameset.htm)です。  
  
 方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]接続を SAP システムでは、次を参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)