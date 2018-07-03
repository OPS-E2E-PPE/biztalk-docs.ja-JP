---
title: BizTalk Adapter for Siebel eBusiness Applications のアーキテクチャの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture of Siebel adapter
- Siebel COM Data Control
- adapters, architecture
ms.assetid: b048937f-207b-4c64-8837-7bfeecedfa03
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b77d1da9261ae4a532e8b56be0f4172350f800e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981443"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>BizTalk Adapter for Siebel eBusiness Applications のアーキテクチャの概要
使用するエンド ツー エンド ソリューションのアーキテクチャについて説明します、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]も、Siebel システムとの内部アーキテクチャで動作する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
 理解、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アーキテクチャに役立ちます。  
  
- 間の関係を理解、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。  
  
- セキュリティの境界を理解して、ソリューション内のデータ セキュリティを強化することができます。  
  
- 理解、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]プロパティをバインドします。  
  
- インストールに関する問題のトラブルシューティングを行います。  

## <a name="adapter-architecture-overview"></a>アダプターのアーキテクチャの概要
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]の上に構築、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]実行時間。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供します、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]とアダプター クライアントのユーザーに豊富な機能を提供するには、採用しています。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム バインドします。 このバインディングには、Siebel システムと通信できるようにする 1 つのカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]によってラップされて、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]実行時間とを介してアプリケーションに公開されて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。  
  
## <a name="siebel-com-data-control"></a>Siebel COM データ コントロール  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel COM データ コントロール ライブラリ (sstchca.dll) と Microsoft.Adapters.Siebel.SiebelBusinessObjectInterface.dll ライブラリを使用して Siebel システムに接続します。 Siebel COM のデータ コントロールは、Siebel Web クライアントのコンポーネントです。 
  
 Siebel COM データ コントロールのインターフェイスのような外部のクライアントを有効にする、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]に接続して、Siebel エンタープライズ サーバー上で Siebel アプリケーション オブジェクト マネージャーと通信します。 Siebel オブジェクト マネージャーと Siebel エンタープライズ サーバーだけでなく他の接続パラメーターがで指定された、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続 URI。 接続 URI の詳細については、次を参照してください。 [Siebel システム接続 URI を使用すると、作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
 次の図は、エンド ツー エンドのアーキテクチャを使用して開発されたソリューションを[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
 ![Siebel エンド&#45;に&#45;アーキテクチャ終了](../../adapters-and-accelerators/adapter-siebel/media/1ae1955e-b7d7-44a0-80c1-1e835edab356.gif "1ae1955e-b7d7-44a0-80c1-1e835edab356")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]として Siebel システムを公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 SOAP メッセージを交換しているクライアント アプリケーションで操作を実行して、Siebel システムのデータにアクセスする、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 上記の図を 4 つの方法を示しています、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]消費されることができます。  
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーション。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して Siebel システムの操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 ソリューションの開発の詳細については、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を使用して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルを参照してください[WCF チャネル モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)します。  
  
- を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーション。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Siebel システムの操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] .NET メソッドとして。 使用することができます、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成するか、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されているメタデータから、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 詳細については、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルと[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[開発 SQL アプリケーションの WCF サービス モデルを使用して](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)します。  
  
- BizTalk 受信場所または送信ポートを Microsoft BizTalk Wcf-custom アダプターを使用するように構成します。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能。 Wcf-custom アダプターを使用して選択し、Siebel のバインドと、受信場所の動作を構成または送信ポートすることができます。 BizTalk のトランザクションは、BizTalk 層チャネル バインド要素、Siebel のバインドのバインド プロパティの設定を読み込むことがでサポートされます。 使用する方法についての詳細、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[、BizTalk アプリケーションの開発](../../core/develop-your-biztalk-applications.md)します。
  
- IIS でホストされる Web サービスを介して。 このシナリオでアダプターを使用して生成された WCF サービスのプロキシは、標準の WCF Http バインドを使用して、IIS でホストされます。 これは、外部ユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、さらに、Siebel システムと通信する、実行時に自動的にアダプターをホストします。  
  
  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel COM のデータ コントロール ライブラリは、常に同じプロセスで、アプリケーションまたはアダプターを使用するサービスをホストするとします。  
  
## <a name="siebel-adapter-and-wcf"></a>Siebel アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] クライアントとサービス間のチャネル上での SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
- *エンドポイント アドレス*メッセージを受信場所を指定します。  
  
- A*バインド*、メッセージ交換に使用される通信プロトコルを指定します。  
  
- A*コントラクト*、エンドポイントによって公開されている操作とデータ型を指定します。  
  
  バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくともバインドは、トランスポートとエンコーディング エンドポイントとメッセージ交換に使用されるを指定する必要があります。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイントのバインドに構成されているバインド要素の 1 つの具象実装です。 [WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデル。  
  
  [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公開、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Siebel のバインド、カスタム バインディング (**Microsoft.Adapters.Siebel.SiebelBinding**)。 このバインディングには既定には、Siebel アダプターのバインド要素の 1 つのカスタム トランスポート バインド要素が含まれています (**Microsoft.Adapters.Siebel.SiebelAdapter**)、Siebel システムで操作できます。 使用する場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、設定することができます、 **EnableBizTalkCompatibilityMode**カスタム バインド要素を読み込むプロパティのバインド-BizTalk 層のチャネル バインド要素: Siebel アダプターの上にバインド要素。 BizTalk 層チャネル バインド要素がによって内部的に実装されている、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel のバインドの外部にさらされることができません。  
  
  **Microsoft.Adapters.Siebel.SiebelBinding** (、Siebel のバインド) と**Microsoft.Adapters.Siebel.SiebelAdapter** (Siebel アダプターのバインド要素) のパブリック クラスは、構成にも公開されますシステム。 Siebel アダプターのバインド要素は一般に公開されるため、独自のカスタムを構築できます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドの機能を拡張できる、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 たとえば、エンタープライズ シングル サインオン (SSO) をサポートするカスタム バインドを実装するで[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービスのモデルのプログラミング。 これを行う理由は、いずれかに。  
  
- 1 つの多機能オペレーション データベースの操作を集計します。  
  
- カスタム アプリケーションによって実装されている操作と Siebel システムの操作の間のスキーマの変換を実行します。  

## <a name="siebel-adapter-and-wcf-lob-adapter-sdk"></a>Siebel アダプターと WCF LOB Adapter SDK

[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]コア コンポーネントのセットを実装します。  
  
- によって提供される機能を活用して、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]します。  
  
- Siebel COM データ コントロール ライブラリ (sstchca.dll) を使用して Siebel システムへの接続を提供します。  
  
  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が使用するソフトウェア レイヤー、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] wcf; インターフェイスSiebel COM データ コントロールは、レイヤー、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムとのインターフェイス。 次の図の内部コンポーネント間の関係を示しています、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]間、およびこれらのコンポーネントと Siebel COM のデータ コントロール。  
  
  ![Siebel アダプターの内部アーキテクチャ](../../adapters-and-accelerators/adapter-siebel/media/e4accea7-86b2-4f2a-937a-edff7e1100ec.gif "e4accea7-86b2-4f2a-937a-edff7e1100ec")
   
## <a name="see-also"></a>参照  
 [Siebel アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
 [BizTalk Adapter for Siebel eBusiness Applications について](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)