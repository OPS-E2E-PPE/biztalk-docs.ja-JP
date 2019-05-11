---
title: BizTalk Adapter for SQL Server の概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e46690e-d5c4-4d6b-b7a0-9a5adf4431cd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a026cabfbfd2dfb846ec3dd2ca27483f5c564fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368505"
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a>BizTalk Adapter for SQL Server の概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF サービスとしての SQL Server データベースを公開します。 アダプター クライアントは、アダプターを使用した SOAP メッセージを交換することで、SQL Server データベースで操作を実行できます。 アダプターは、SOAP メッセージを使用し、操作を実行する適切な ADO.NET 呼び出しを行います。 アダプターは、SOAP メッセージの形式でクライアントに SQL Server データベースからの応答を返します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (テーブル、ビュー、およびプロシージャ) などの SQL Server データベースのアイテムのサーフェスのメタデータ。  このメタデータには、Web サービス記述言語 (WSDL) の形式で SOAP メッセージの構造について説明します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアントの操作のメタデータを取得できるようにします。 アダプターには、プログラミング ソリューションで使用できるプログラミングの成果物も生成されます。 詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ADO.NET を使用して、SQL Server データベースと通信します。 使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の方法で SQL Server データベースと通信します。  
  
- BizTalk アプリケーションを開発しています。 詳細については、次を参照してください。[開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)します。  
  
- 使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。 詳細については、次を参照してください。 [WCF サービス モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)します。  
  
- WCF チャネル モデルを使用します。 詳細については、次を参照してください。 [WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプターは、SQL Server にどのように接続しますか。](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [アダプターのサーフェスの SQL サーバーのメタデータをどのようにか。](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [SQL アダプターによってサポートされる操作](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server を理解する](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)