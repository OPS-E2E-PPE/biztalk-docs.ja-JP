---
title: メタデータと、WCF サービスの Oracle Database によるモデル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service model, metadata
- WCF client class
- WCF service contract
ms.assetid: b55cf4ed-c41a-4986-bbaf-88e80c32b01f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0068fbac2f1ee59cd367799b5e44a3d545063380
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376369"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a>メタデータと Oracle Database による WCF サービス モデル
WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラスを生成するコードでは使用できますか。  
  
- 操作 (WCF クライアント クラス) のアダプターを呼び出す  
  
- 受信アダプター (WCF サービス コントラクト) からの操作  
  
  これらのツールによって公開されているメタデータからのターゲットの操作 (だけでなく、サポートのメッセージ コントラクト、操作コントラクト、およびデータ コントラクト) のサービス コントラクトを表す .NET クラスの生成、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 生成されたこの構造を理解したりコードは、「生成されたクライアント コードを理解する」をご覧[ http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)します。 このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。 WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle データベースの WCF クライアントまたは WCF サービス コントラクトを生成します。ソリューションの成果物](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベースのアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)