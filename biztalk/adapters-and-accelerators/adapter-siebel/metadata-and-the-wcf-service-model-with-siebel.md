---
title: "メタデータと、WCF サービスの Siebel 使用モデルの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, metadata
- metadata, and the WCF service model
ms.assetid: 3aca1835-fb9e-4841-a920-078da0b3fe76
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed348c2ab183960b7af1383768259f67c4ca6270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a>メタデータと Siebel で WCF サービスのモデル
使用する WCF サービス モデルで、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラスを生成する: WCF クライアント クラス — をコードできます操作の呼び出しで使用、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。  
  
 これらのツールでは、アダプターによって公開されるメタデータを使用して、生成します。  
  
-   ターゲットのサービス コントラクトを表す注釈付き .NET インターフェイスです。 このインターフェイスは、WCF サービス コントラクトと呼ばれます。  
  
-   サポートのメッセージ コントラクト、操作コントラクトおよびサービス コントラクト用のデータ コントラクトを表す注釈付きのクラスです。  
  
-   WCF クライアント クラスを WCF サービス コントラクトによって公開されるサービスのメソッド (操作) を呼び出すメソッドを使用できます。  
  
 生成されたこの構造についてのヘルプのコードを参照してください「生成されたクライアント コードを理解する」で[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)です。 このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
 ターゲットの WCF クライアント クラスを生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは WCF サービス コントラクトを Siebel ソリューションの成果物の生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)