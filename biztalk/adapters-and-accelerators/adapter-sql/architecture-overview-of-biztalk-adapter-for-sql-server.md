---
title: BizTalk Adapter for SQL Server のアーキテクチャの概要 |Microsoft ドキュメント
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
ms.openlocfilehash: 841f07bfb8c027ab2bfc1b98e23b225af42b449c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225250"
---
# <a name="architecture-overview-of-biztalk-adapter-for-sql-server"></a>BizTalk Adapter for SQL Server のアーキテクチャの概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 このバインディングには、SQL Server データベースとの通信を有効にする単一のカスタム トランスポート バインド要素が含まれています。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]によってラップされた、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]実行時間とは経由でアプリケーションに公開される、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ADO.NET を使用して、SQL Server データベースと通信します。  


 次の図を使用して開発されたソリューションをエンド ツー エンド アーキテクチャを示しています、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/05e2a88c-a3cc-42a7-9c06-cfdb7c071e70.gif "05e2a88c-a3cc-42a7-9c06-cfdb7c071e70")  

  
## <a name="consuming-the-adapter"></a>アダプターの使用  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]として SQL Server データベースの公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアント アプリケーション サービスです。 操作を実行し、SQL Server データベースのデータにアクセス、クライアント アプリケーションが SOAP メッセージを交換、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を通じて[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル。 上記の図に 4 つの方法を示しています、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]消費されることができます。  
  
-   **を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル アプリケーション**です。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルのアプリケーションを使用して SQL Server データベースで操作を実行する、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SOAP 交換をチャネル モデルを直接使用してメッセージ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 参照してください[WCF チャネル モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)です。
  
-   **を介して、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル アプリケーション**です。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデルのアプリケーションのメソッドを呼び出して、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] SQL Server データベースで操作を実行するクライアント。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントによって公開される操作をモデル化、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] .NET メソッドとして。 使用することができます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]または WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスによって公開されるメタデータから、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  参照してください[WCF サービス モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)です。
  
-   **BizTalk 受信場所または送信ポートは、Microsoft BizTalk Wcf-custom アダプターを使用するようを**です。 Wcf-custom アダプターが使用できるように[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]拡張機能です。 WCF カスタム アダプターを使用して選択し、SQL DB バインドと、受信場所の動作を構成したり、送信ポートできます。 使用する方法についての詳細、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)です。 
  
-   **IIS でホストされる Web サービスを介して**です。 このシナリオでは、アダプターを使用して生成された WCF サービス プロキシは標準の WCF Http バインドを使用して IIS でホストされます。 これは、外部のユーザーに Web サービスとして、サービス コントラクトを公開します。 IIS は、さらに、SQL Server データベースと通信する、実行時に自動的にアダプターをホストします。  
  
## <a name="the-sql-adapter-and-wcf"></a>SQL アダプターと WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントとサービス間のチャネル上で SOAP メッセージの交換に基づくプログラミング モデルを表示します。 これらのメッセージは、通信しているクライアントとサービスによって公開されるエンドポイント間で送信されます。 エンドポイントで構成されます。  
  
-   *エンドポイント アドレス*メッセージが受信場所を指定します。  
  
-   A*バインディング*、メッセージ交換に使用する通信プロトコルを指定します。  
  
-   A*コントラクト*、エンドポイントによって公開される操作とデータ型を指定します。  
  
 バインディングは、積み重ねられて、エンドポイントでメッセージを交換する方法を定義する 1 つまたは複数のバインド要素で構成されます。 少なくとも、バインディングはトランスポートとエンドポイントにメッセージを交換するために使用されるエンコーディングを指定します。 メッセージ交換のエンドポイント間では、1 つまたは複数のチャネルを構成しているチャネル スタックを介して行われます。 各チャネルは、エンドポイント用に構成されたバインディングのバインド要素の 1 つの具象実装です。 

[WCF ドキュメント](http://go.microsoft.com/fwlink/?LinkID=196850)に関する詳細が含まれます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]プログラミング モデルです。  
  
 [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公開、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]カスタムのバインディングでは、SQL DB バインド (**Microsoft.Adapters.SQLDB.SQLDBBinding**)。 既定では、このバインディングに 1 つのカスタム トランスポート バインド要素、SQL DB のアダプターのバインド要素が含まれています (**Microsoft.Adapters.SQLDB.SQLDBAdapter**)、SQL Server データベースでの操作を有効にします。  
  
 **Microsoft.Adapters.SQLDB.SQLDBBinding** (、SQL DB バインディング) および**Microsoft.Adapters.SQLDB.SQLDBAdapter** (SQL DB アダプターのバインド要素) のパブリック クラスは、構成システムにも公開されます。 SQL DB アダプターのバインド要素がパブリックに公開されているため、独自のカスタムをビルドすることができます[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]バインディングの機能を拡張するための対応、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 たとえばでエンタープライズ シングル サインオン (SSO) をサポートするカスタム バインディングを実装する可能性があります、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルまたはサービス モデルのソリューションです。 これを行うための理由は、1 つの多機能オペレーションまたはカスタム アプリケーションによって実装される操作と、SQL Server データベースに対する操作の間でのスキーマの変換を実行する集計のデータベース操作になります。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の上に構築された、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、上で実行し、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]実行時間。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ソフトウェア フレームワークとツールのインフラストラクチャを提供、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用してユーザーとアダプターのクライアントに各種の機能を提供します。  

## <a name="sql-adapter-and-the-wcf-lob-adapter-sdk"></a>SQL アダプターと WCF LOB Adapter SDK
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]によって提供される機能を活用するコア コンポーネントのセットが実装されて、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ADO.NET を使用して、SQL Server データベースへの接続を提供します。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 、ソフトウェアのレイヤーの役割を果たす、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インターフェイスを持つ、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。ADO.NET を使用するレイヤーとして機能、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースを持つインターフェイスです。 次の図の内部コンポーネント間の関係を示しています、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]およびこれらのコンポーネントと ADO.NET の間です。  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/0b15e33b-7f59-4228-bb50-0455f7ed3d85.gif "0b15e33b-7f59-4228-bb50-0455f7ed3d85")  
 
   
## <a name="adonet"></a>ADO.NET  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ADO.NET を使用して、SQL Server データベースを使用して接続します。 ADO.NET では、SQL Server などのデータ ソースに一貫してアクセスを提供し、取得、処理、およびデータ ソースのデータの変更が容易になります。 詳細について[ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx)です。
  
 SQL クライアントでは、SQL Server データベースへの接続を提供します。 接続 URI を提供することによって、SQL Server データベースへの接続を確立する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 この接続 URI には、SQL Server がインストールされているコンピューターの名前と、データベースの名前。 接続 URI の詳細については、次を参照してください。 [SQL Server への接続を作成する](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)です。  
  
## <a name="see-also"></a>参照  

 [SQL Server の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)