---
title: WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す |Microsoft Docs
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
ms.openlocfilehash: 607a9188d53c1f18e40c04f6b7f692098dfc738c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369315"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントは、ストアド プロシージャを呼び出すには、WCF クライアントで呼び出すことができますの操作として、ストアド プロシージャを検出します。 ストアド プロシージャが結果セットを返す方法に基づき、アダプターとしてすべてのストアド プロシージャを示しています。  
  
- **プロシージャ**します。 ストアド プロシージャを呼び出し、**プロシージャ**ノードは、データセットの配列を返します。  
  
- **厳密に型指定されたプロシージャ**します。 ストアド プロシージャを呼び出し、 **Strongly-Typed プロシージャ**ノードは、厳密に型指定された結果セットを返します。  
  
  接続されているデータベースのストアド プロシージャの同じセットは、両方の下に表示されている、**プロシージャ**と**Strongly-Typed プロシージャ**ノード。 目的の結果セットの種類に基づいて、関連するノードからストアド プロシージャを呼び出す必要があります。 方法の詳細については[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャをサポートするを参照してください[BizTalk Server を使用して SQL Server でのストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)します。  
  
  このセクションでは、両方のストアド プロシージャを呼び出す方法の説明、**プロシージャ**と**Strongly-Typed プロシージャ**WCF クライアントを使用してノード。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Involk 厳密に型指定の WCF サービス モデルを使用して SQL ストアド プロシージャ](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SQL を厳密に型指定のストアド プロシージャを呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)