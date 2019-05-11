---
title: メタデータと、WCF サービス モデルで SAP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f120d2d93dcfe56595c020a4032c4d714afc5c90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373191"
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a>メタデータと SAP を含む WCF サービス モデル
WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラスを生成するコードでは使用できますか。  
  
- 操作 (WCF クライアント クラス) のアダプターを呼び出す  
  
- 受信アダプター (WCF サービス コントラクト) からの操作  
  
  これらのツールによって公開されているメタデータからのターゲットの操作 (だけでなく、サポートのメッセージ コントラクト、操作コントラクト、およびデータ コントラクト) のサービス コントラクトを表す .NET クラスの生成、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。 この生成されたコードの構造を理解したり、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)します。 このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。 WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) のターゲットの操作を生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[for SAP の WCF クライアントまたは WCF サービス コントラクトの生成ソリューションの成果物](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)