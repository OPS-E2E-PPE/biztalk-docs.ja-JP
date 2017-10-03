---
title: "BizTalk Adapter for SQL Server の概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e46690e-d5c4-4d6b-b7a0-9a5adf4431cd
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d0c1fd3ce3a9f07367b7cc75ffeeb98f84b119
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a>BizTalk Adapter for SQL Server の概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]を WCF サービスとしての SQL Server データベースを公開します。 アダプターのクライアントは、アダプターと SOAP メッセージを交換することで、SQL Server データベースでの操作を実行できます。 アダプターは、SOAP メッセージを処理し、操作を実行する適切な ADO.NET 呼び出しします。 アダプターは、SOAP メッセージの形式でクライアントに、SQL Server データベースからの応答を返します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (テーブル、ビュー、およびプロシージャ) など、SQL Server データベースのアイテムのサーフェス メタデータ。  このメタデータは、Web サービス記述言語 (WSDL) の形式で SOAP メッセージの構造を記述します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアント操作のメタデータを取得できるようにします。 アダプターでは、プログラミング ソリューションで使用できるプログラミングの成果物も生成します。 詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)です。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ADO.NET を使用して、SQL Server データベースと通信します。 使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次のように、SQL Server データベースと通信します。  
  
-   BizTalk アプリケーションを開発することによりします。 詳細については、次を参照してください。[開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)です。  
  
-   使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。 詳細については、次を参照してください。 [WCF サービス モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデルを使用します。 詳細については、次を参照してください。 [WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプターは、SQL Server にどのように接続しますか。](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [アダプターの表面の SQL サーバーのメタデータをどのようにしますか。](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [どのような操作、SQL アダプターによってサポートされます。](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a>参照  
 [SQL Server の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)