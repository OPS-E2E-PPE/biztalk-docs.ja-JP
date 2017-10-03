---
title: "メタデータと、WCF サービスの SAP とモデル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f06cd33c0776df70e5ff2554d355915908012abb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a>メタデータと SAP と WCF サービスのモデル
WCF サービス モデルで使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラス生成に使用するコードはできますか。  
  
-   アダプター (WCF クライアント クラス) に対する操作を呼び出す  
  
-   受信アダプター (WCF サービス コントラクト) からの操作  
  
 これらのツールによって公開されるメタデータから操作を指定 (だけでなく、メッセージ コントラクトをサポートする、操作コントラクト、およびデータ コントラクト) のサービス コントラクトを表す .NET クラスを生成する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。 ヘルプについては、この生成されたコードの構造を理解するうえで、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)です。 このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。 WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) のターゲットの操作を生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[for SAP の WCF クライアントまたは WCF サービス コントラクトの生成ソリューションの成果物](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)