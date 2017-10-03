---
title: "メタデータと、WCF サービスの Oracle E-business Suite でモデル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d3fcba-c72f-4ae9-82bd-abbfc2a0c2c4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cf87c0a579d1f0c0de590d78e559ead73be0cec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-e-business-suite"></a>メタデータおよび Oracle E-business Suite では、WCF サービスのモデル
WCF サービス モデルで使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) を次を行うには。  
  
-   サービス コントラクトを生成します: WCF サービス コントラクト: 使用する、コードは、アダプターから操作を受け取ることができます。 この .NET インターフェイスは、操作を指定のサービス コントラクトを表します。  
  
-   プロキシ クラスを生成: WCF クライアント クラス — 使用されるコードが、アダプターでの操作を呼び出すことができます。  
  
-   サポートのメッセージ コントラクト、操作コントラクトおよびサービス コントラクト用のデータ コントラクトを表す注釈付きのクラスです。  
  
 生成されたこの構造についてのヘルプのコードを参照してください「生成されたクライアント コードを理解する」で[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)です。 このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
 WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle E-business の WCF クライアントまたは WCF サービス コントラクトを生成Suite ソリューションの成果物](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite アプリケーションの開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)