---
title: BizTalk Adapter for Siebel eBusiness Applications について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 788db9ba048141256cfaa3cc5017fa48bd6ec7de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999235"
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a>BizTalk Adapter for Siebel eBusiness Applications についてください。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを使用します。 アダプターは、次の利点をクライアントに提供します。  
  
- **デザイン時エクスペリエンスの一貫性のある**します。 アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的な使いやすいもののデザイン時のエクスペリエンスを提供します。  
  
- **プログラミングのオプションをさまざまな**します。 アダプターは、Windows Communication Foundation (WCF) などのプログラミング モデルの選択肢を提供するチャネル モデルでは、WCF サービス モデルでは、ADO.NET、Web サービス、または BizTalk には、モデルがサポートされています。  
  
- **Lob の間でのエクスペリエンス、統一された**します。 アダプターが、WCF を使用して標準と[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。  
  
  前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。 WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。 WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。 WCF LOB Adapter SDK の詳細については、次を参照してください。 [WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)します。
  
  Siebel システムの操作を実行するには、アダプター クライアントは、Siebel システムによって公開されるビジネス サービスにアクセスする必要があります。 Siebel アプリケーションでは、ビジネス コンポーネントおよびビジネス オブジェクトとしてデータを公開します。 Siebel*ビジネス コンポーネント*を 1 つまたは複数のテーブルの列を 1 つの構造に関連付ける論理エンティティです。 Siebel*ビジネス オブジェクト*一連の相互に関連するビジネス コンポーネントの連携により、ビジネス モデルを実装します。 [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]、アダプター クライアントは、Siebel ビジネス オブジェクトおよびビジネス コンポーネントを表示できます。  
  
  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]も含まれています、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET インターフェイスを拡張することで Siebel システムへの ADO インターフェイスを提供します。  
  
  このセクションには、機能がについて説明します、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Adapter for Siebel eBusiness Applications の概要](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Siebel アダプターの主要な機能](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [BizTalk Adapter for Siebel eBusiness Applications の制限事項](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Data Provider for Siebel について](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)