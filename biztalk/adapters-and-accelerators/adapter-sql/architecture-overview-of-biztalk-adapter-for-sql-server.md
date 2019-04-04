---
title: BizTalk Adapter for SQL Server のアーキテクチャの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d31eb73f-b73e-4cd3-8b62-207b806175ee
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37b5a21380b3883967e4478940ee7abbee6760c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995491"
---
# <a name="architecture-overview-of-biztalk-adapter-for-sql-server"></a>BizTalk Adapter for SQL Server のアーキテクチャの概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 このバインディングには、SQL Server データベースとの通信を実現する 1 つのカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]によってラップされて、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]実行時間とを介してアプリケーションに公開されて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ADO.NET を使用して、SQL Server データベースと通信します。  


 次の図は、エンド ツー エンドのアーキテクチャを使用して開発されたソリューションを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/05e2a88c-a3cc-42a7-9c06-cfdb7c071e70.gif "05e2a88c-a3cc-42a7-9c06-cfdb7c071e70")  

  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]として SQL Server データベースを公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 クライアント アプリケーションが SOAP メッセージを交換する操作を実行し、SQL Server データベースのデータにアクセスを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 上記の図を 4 つの方法を示しています、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]消費されることができます。  
  
- **を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル アプリケーション**します。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して SQL Server データベースの操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 参照してください[WCF チャネル モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)します。
  
- **を通じて、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル アプリケーション**します。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント、SQL Server データベースで操作を実行します。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されているメタデータから、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  参照してください[開発 SQL アプリケーションの WCF サービス モデルを使用して](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)します。
  
- **BizTalk 受信場所または送信ポート、Microsoft BizTalk Wcf-custom アダプターを使用するように構成された**します。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能。 Wcf-custom アダプターを使用して選択し、SQL DB のバインドと、受信場所の動作を構成または送信ポートすることができます。 使用する方法についての詳細、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)します。 
  
- **IIS でホストされる Web サービスを介して**します。 このシナリオでアダプターを使用して生成された WCF サービスのプロキシは、標準の WCF Http バインドを使用して、IIS でホストされます。 これは、外部ユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、さらに、SQL Server データベースと通信する、実行時に自動的にアダプターをホストします。  
  
## <a name="the-sql-adapter-and-wcf"></a>SQL アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] クライアントとサービス間のチャネル上での SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
- *エンドポイント アドレス*メッセージを受信場所を指定します。  
  
- A*バインド*メッセージを交換するために使用する通信プロトコルを指定します。  
  
- A*コントラクト*、エンドポイントによって公開される操作とデータ型を指定します。  
  
  バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくともバインドは、トランスポートとエンコーディング エンドポイントとメッセージ交換に使用されるを指定する必要があります。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングでバインド要素の 1 つの具象実装です。 

[WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデル。  
  
 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公開、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SQL DB のバインド、カスタム バインディング (**Microsoft.Adapters.SQLDB.SQLDBBinding**)。 このバインディングには既定では、SQL DB アダプターのバインド要素の 1 つのカスタム トランスポート バインド要素が含まれています (**Microsoft.Adapters.SQLDB.SQLDBAdapter**)、SQL Server データベースで操作できます。  
  
 **Microsoft.Adapters.SQLDB.SQLDBBinding** (、SQL DB のバインド) と**Microsoft.Adapters.SQLDB.SQLDBAdapter** (SQL DB アダプターのバインド要素) のパブリック クラスは、構成システムにも公開されます。 SQL DB アダプターのバインド要素は一般に公開されるため、独自のカスタムを構築できます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインドの機能を拡張できる、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 たとえば、エンタープライズ シングル サインオン (SSO) をサポートするカスタム バインドを実装するで、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービスのモデル ソリューション。 これを行う理由は、1 つの多機能オペレーションまたはカスタム アプリケーションによって実装される操作と、SQL Server データベースに対する操作の間のスキーマの変換を実行する集計のデータベース操作になります。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の上に構築、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]実行時間。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供します、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用してユーザーとアダプター クライアントに豊富な機能を提供します。  

## <a name="sql-adapter-and-the-wcf-lob-adapter-sdk"></a>SQL アダプターと WCF LOB Adapter SDK
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]によって提供される機能を利用するコア コンポーネントのセットを実装、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ADO.NET を使用して、SQL Server データベースへの接続を提供します。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]するソフトウェア レイヤーとして機能、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]とのインターフェイス、 [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)];ADO.NET は、レイヤーとして機能、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースとのインターフェイス。 次の図の内部コンポーネント間の関係を示しています、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]とこれらのコンポーネントと ADO.NET の間。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/0b15e33b-7f59-4228-bb50-0455f7ed3d85.gif "0b15e33b-7f59-4228-bb50-0455f7ed3d85")  
 
   
## <a name="adonet"></a>ADO.NET  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ADO.NET を使用して、SQL Server データベースに接続します。 ADO.NET は、SQL Server などのデータ ソースに一貫してアクセスを提供し、取得、処理、およびデータ ソース内のデータの変更を容易にします。 詳細をご覧ください[ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx)します。
  
 SQL クライアントでは、SQL Server データベースへの接続を提供します。 接続 URI を提供することで、SQL Server データベースへの接続を確立する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 この接続の URI には、SQL Server がインストールされているコンピューターの名前とデータベースの名前。 接続 URI の詳細については、[SQL Server への接続を作成する](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)を参照してください。  
  
## <a name="see-also"></a>参照  

 [BizTalk Adapter for SQL Server を理解する](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)