---
title: メタデータと、SQL アダプターで WCF サービス モデル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a046615fb458991f51784f1059de609d1b3c73a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368721"
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a>メタデータと、SQL アダプターで WCF サービス モデル
WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、以下の ServiceModel メタデータ ユーティリティ ツール (svcutile.exe)。  
  
- サービス コントラクトの生成: WCF サービス コントラクト: により、コードは、アダプターから操作を受信できます。 この .NET インターフェイスでは、ターゲットのサービス コントラクトを表します。  
  
- プロキシ クラスを生成、WCF クライアント クラス-コードにより、アダプターでの操作を呼び出すことができます。  
  
- サポートのメッセージ コントラクト、操作のコントラクト、およびサービス コントラクト用のデータ コントラクトを表す注釈クラス。  
  
  この生成されたコードの構造を理解したり、次を参照してください。[生成されたクライアント コードを理解する](https://msdn.microsoft.com/library/ms733881.aspx)します。 このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
  WCF クライアント クラスまたはターゲットの操作のための WCF サービス コントラクトを生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)