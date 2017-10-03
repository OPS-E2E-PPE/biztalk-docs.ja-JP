---
title: "BizTalk Adapter for Siebel eBusiness Applications のアーキテクチャの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture of Siebel adapter
- Siebel COM Data Control
- adapters, architecture
ms.assetid: b048937f-207b-4c64-8837-7bfeecedfa03
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d78bf2104d5383f3c8aa34984a5781fa8f4dbfb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>BizTalk Adapter for Siebel eBusiness Applications のアーキテクチャの概要
使用するエンド ツー エンド ソリューションのアーキテクチャについて説明、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]も、Siebel システムと内部のアーキテクチャで動作する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
 理解、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アーキテクチャに役立ちます。  
  
-   関係を理解、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。  
  
-   ソリューション内のデータのセキュリティを改善できるように、セキュリティ境界を理解します。  
  
-   理解、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]プロパティをバインドします。  
  
-   インストールに関する問題のトラブルシューティングを行います。  

## <a name="adapter-architecture-overview"></a>アダプターのアーキテクチャの概要
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]の上に構築された、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]実行時間。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ユーザーとアダプターのクライアントを機能豊富な一連の機能を提供する使用します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム バインドがします。 このバインディングには、Siebel システムとの通信を有効にする単一のカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]によってラップされた、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]実行時間とは経由でアプリケーションに公開される、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。  
  
## <a name="siebel-com-data-control"></a>Siebel COM データ コントロール  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel COM データ コントロール ライブラリ (sstchca.dll) と Microsoft.Adapters.Siebel.SiebelBusinessObjectInterface.dll ライブラリを通じて、Siebel システムに接続します。 Siebel COM データ コントロールは、Siebel Web クライアントのコンポーネントです。 
  
 Siebel COM データ コントロールのインターフェイスのような外部のクライアントを有効にする、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]に接続して Siebel エンタープライズ サーバーの Siebel アプリケーション オブジェクト マネージャーと通信します。 Siebel オブジェクト マネージャーと Siebel エンタープライズ サーバーだけでなく他の接続パラメーターで指定された、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続 URI。 接続 URI の詳細については、次を参照してください。 [Siebel システム接続 URI を作成する](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
 次の図を使用して開発されたソリューションをエンド ツー エンド アーキテクチャを示しています、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
 ![Siebel エンド &#45; へ (& a) #45 です。アーキテクチャを終了](../../adapters-and-accelerators/adapter-siebel/media/1ae1955e-b7d7-44a0-80c1-1e835edab356.gif "1ae1955e-b7d7-44a0-80c1-1e835edab356")  
  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]として Siebel システムを公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 操作を実行し、Siebel システムのデータにアクセス、クライアント アプリケーションが SOAP メッセージを交換、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 上記の図に 4 つの方法を示しています、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]消費されることができます。  
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル アプリケーションです。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して、Siebel システムでの操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 ソリューションの開発の詳細については、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を使用して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデルをチャネルは、「 [WCF チャネル モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)です。  
  
-   を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル アプリケーション サービスを提供します。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] Siebel システムに対して操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] .NET メソッドとして。 使用することができます、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成するか、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されるメタデータから、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 詳細については、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルと[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[WCF サービス モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)です。  
  
-   BizTalk 受信場所または Microsoft BizTalk Wcf-custom アダプターを使用して構成されているポートを送信します。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能です。 WCF カスタム アダプターを使用して選択し、Siebel のバインドと、受信場所の動作を構成したり、送信ポートできます。 BizTalk トランザクションは、BizTalk 層チャネル バインド要素、Siebel のバインドにバインドするプロパティを設定して読み込むことができますでサポートされます。 使用する方法についての詳細、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[、BizTalk アプリケーションの開発](../../core/develop-your-biztalk-applications.md)です。
  
-   IIS でホストされる Web サービスを介して。 このシナリオでは、アダプターを使用して生成された WCF サービス プロキシは標準の WCF Http バインドを使用して IIS でホストされます。 これは、外部のユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、Siebel システムと通信する、実行時に自動的にアダプターをホストします。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel COM データ コントロール ライブラリは、常にホストのプロセスで、アプリケーションまたはサービス アダプターを使用するとします。  
  
## <a name="siebel-adapter-and-wcf"></a>Siebel アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントとサービス間のチャネル上で SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
-   *エンドポイント アドレス*メッセージが受信場所を指定します。  
  
-   A*バインディング*メッセージの交換に使用する通信プロトコルを指定します。  
  
-   A*コントラクト*、エンドポイントによって公開されている操作とデータ型を指定します。  
  
 バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくとも、バインディングはトランスポートとエンドポイントにメッセージを交換するために使用されるエンコーディングを指定します。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されているバインディングのバインド要素の 1 つの具象実装です。 [WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデルです。  
  
 [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]カスタム バインド、Siebel のバインド (**Microsoft.Adapters.Siebel.SiebelBinding**)。 既定では、このバインディングに 1 つのカスタム トランスポート バインド要素、Siebel アダプターのバインド要素が含まれています (**Microsoft.Adapters.Siebel.SiebelAdapter**)、Siebel システムの操作を有効にします。 使用する場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、設定することができます、 **EnableBizTalkCompatibilityMode**バインディング プロパティをカスタム バインド要素を読み込む: BizTalk 層チャネル バインド要素: Siebel アダプターの上にバインド要素。 BizTalk 層チャネル バインド要素がによって内部的に実装されている、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel バインディングは、外部に公開されていないとします。  
  
 **Microsoft.Adapters.Siebel.SiebelBinding** (、Siebel のバインド) と**Microsoft.Adapters.Siebel.SiebelAdapter** (Siebel アダプターのバインド要素) のパブリック クラスは、構成には公開されていますシステムです。 Siebel アダプターのバインド要素がパブリックに公開されているため、独自のカスタムをビルドすることができます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインディングの機能を拡張するための対応、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 たとえば、エンタープライズ シングル サインオン (SSO) をサポートするカスタム バインディングを実装してででした[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービスのモデルのプログラミング。 これを行う理由は、いずれかに。  
  
-   1 つの多機能オペレーション データベースの操作を集計します。  
  
-   スキーマのカスタム アプリケーションによって実装される操作と Siebel システムの操作間で変換を実行します。  

## <a name="siebel-adapter-and-wcf-lob-adapter-sdk"></a>Siebel アダプターと WCF LOB Adapter SDK

[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]コア コンポーネントのセットを実装します。  
  
-   によって提供される機能を活用して、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。  
  
-   Siebel COM データ コントロール ライブラリ (sstchca.dll) を通じて Siebel システムへの接続を提供します。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は、ソフトウェアのレイヤーであり、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF; を持つインターフェイスSiebel COM データ コントロールは、レイヤーであり、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムを持つインターフェイスです。 次の図の内部コンポーネント間の関係を示しています、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]間およびこれらのコンポーネントと Siebel COM データ コントロールです。  
  
 ![Siebel アダプターの内部アーキテクチャ](../../adapters-and-accelerators/adapter-siebel/media/e4accea7-86b2-4f2a-937a-edff7e1100ec.gif "e4accea7-86b2-4f2a-937a-edff7e1100ec")
   
## <a name="see-also"></a>参照  
 [Siebel アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
 [Siebel eBusiness Applications の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)