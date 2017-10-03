---
title: "メタデータと、SQL アダプターで WCF サービス モデル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95ed3188c01f0f6d568bd745decd9e601e6ee3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a>メタデータと、SQL アダプターで WCF サービス モデル
WCF サービス モデルで使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) を次を行うには。  
  
-   サービス コントラクトを生成します: WCF サービス コントラクト: 使用する、コードは、アダプターから操作を受け取ることができます。 この .NET インターフェイスは、操作を指定のサービス コントラクトを表します。  
  
-   プロキシ クラスを生成: WCF クライアント クラス — 使用されるコードが、アダプターでの操作を呼び出すことができます。  
  
-   サポートのメッセージ コントラクト、操作コントラクトおよびサービス コントラクト用のデータ コントラクトを表す注釈付きのクラスです。  
  
 ヘルプについては、この生成されたコードの構造を理解するうえで、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)です。 このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
 WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)