---
title: サービスの Oracle データベースとモデルのメタデータと、WCF |Microsoft ドキュメント
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
ms.openlocfilehash: 76933dba64e6e8bb75eb0394ab8e6eedd3fb7116
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214978"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a>メタデータおよび Oracle データベースと、WCF サービスのモデル
WCF サービス モデルで使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutile.exe) プロキシ クラス生成に使用するコードはできますか。  
  
-   アダプター (WCF クライアント クラス) に対する操作を呼び出す  
  
-   受信アダプター (WCF サービス コントラクト) からの操作  
  
 これらのツールによって公開されるメタデータから操作を指定 (だけでなく、メッセージ コントラクトをサポートする、操作コントラクト、およびデータ コントラクト) のサービス コントラクトを表す .NET クラスを生成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 生成されたこの構造についてのヘルプのコードを参照してください「生成されたクライアント コードを理解する」で[http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)です。 このトピックでは、コード svcutil.exe が生成されますが、そのコンテンツがコードに該当するも特にについて説明する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。 WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法の詳細および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Oracle データベースの WCF クライアントまたは WCF サービス コントラクトを生成ソリューションの成果物](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)