---
title: WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2d707c37ba92fb6f1d1608ae43d02d1e964cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222290"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントは、ストアド プロシージャを呼び出す、WCF クライアントで呼び出すことができますの操作として、ストアド プロシージャを検出します。 ストアド プロシージャが結果セットを返す方法に基づき、アダプターは、すべてのストアド プロシージャとしてを分類します。  
  
-   **プロシージャ**です。 ストアド プロシージャを呼び出して、**プロシージャ**ノードは、データセットの配列を返します。  
  
-   **厳密に型指定されたプロシージャ**です。 ストアド プロシージャを呼び出して、 **Strongly-Typed プロシージャ**ノードは、厳密に型指定された結果セットを返します。  
  
 接続されているデータベースのストアド プロシージャの同じセットは、両方の下の一覧を表示、**プロシージャ**と**Strongly-Typed プロシージャ**ノード。 目的の結果セットの種類に基づいて、関連するノードからストアド プロシージャを呼び出す必要があります。 方法の詳細については[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャをサポートするを参照してください[BizTalk Server を使用して SQL Server でストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)です。  
  
 このセクションでは 2 つのストアド プロシージャを呼び出す方法について説明、**プロシージャ**と**Strongly-Typed プロシージャ**ノードでは、WCF クライアントを使用します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF サービス モデルを使用して sql Involk 弱い型指定のストアド プロシージャ](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [WCF サービスのモデルを使用して SQL での厳密に型指定のストアド プロシージャを呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)