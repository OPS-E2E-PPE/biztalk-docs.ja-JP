---
title: メタデータと、WCF サービス モデルで Siebel |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, metadata
- metadata, and the WCF service model
ms.assetid: 3aca1835-fb9e-4841-a920-078da0b3fe76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73fdf3b57756bb2dfc007e63f803bf17c29285ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976651"
---
# <a name="metadata-and-the-wcf-service-model-with-siebel"></a>メタデータと Siebel と WCF サービス モデル
WCF サービス モデルを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]またはプロキシ クラスを生成する ServiceModel メタデータ ユーティリティ ツール (svcutile.exe): WCF クライアント クラス-するコードは操作を呼び出してから、 [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
 これらのツールでは、アダプターによって公開されているメタデータを使用して、生成します。  
  
- ターゲットのサービス コントラクトを表す注釈付き .NET インターフェイス。 このインターフェイスは、WCF サービス コントラクトと呼ばれます。  
  
- サポートのメッセージ コントラクト、操作のコントラクト、およびサービス コントラクト用のデータ コントラクトを表す注釈クラス。  
  
- WCF クライアント クラス メソッドを持つ WCF サービス コントラクトによって公開されているサービス メソッド (操作) の呼び出しに使用できます。  
  
  生成されたこの構造を理解したりコードは、「生成されたクライアント コードを理解する」をご覧[ http://go.microsoft.com/fwlink/?LinkId=98365](http://go.microsoft.com/fwlink/?LinkId=98365)します。 このトピックでは、svcutil.exe が生成されますが、そのコンテンツがコードに該当するものコードを具体的に説明する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]が生成されます。  
  
  操作の対象の WCF クライアント クラスを生成する方法について、および svcutil.exe の相違点について、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[WCF クライアントまたは WCF サービス コントラクトの Siebel ソリューションの成果物の生成](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)