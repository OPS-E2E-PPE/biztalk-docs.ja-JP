---
title: BizTalk Adapter for mySAP Business Suite について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 709833ecec71a98e0e09d2cd660b68bf5b647d8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985611"
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a>BizTalk Adapter for mySAP Business Suite についてください。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを使用します。 アダプターは、次の利点をクライアントに提供します。  
  
- **デザイン時エクスペリエンスの一貫性のある**します。 アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的な使いやすいもののデザイン時のエクスペリエンスを提供します。  
  
- **プログラミングのオプションをさまざまな**します。 アダプターは、さまざまなプログラミング モデルの Windows Communication Foundation (WCF) チャネル モデルを含む、WCF サービス モデル、ADO.NET、web サービス、または BizTalk がサポートされているモデルを提供します。  
  
- **Lob の間でのエクスペリエンス、統一された**します。 アダプターが、WCF を使用して標準と[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]し、そのため、LOB システムへのアクセスのエクスペリエンスの一貫性を提供します。  
  
  前述のように、アダプターは WCF LOB Adapter SDK の上に構築されます。 WCF LOB Adapter SDK は、さまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションが使用できる統合アダプターを構築するための共通の基盤を提供します。 WCF LOB Adapter SDK は、Windows Communication Foundation (WCF) チャネルとしての統合アダプターを公開することで、Microsoft のサービスを使用したアダプターの戦略を配置します。 WCF LOB Adapter SDK の詳細については、次を参照してください。 [WCF LOB Adapter SDK ドキュメント](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)します。
  
  SAP システムの操作を実行するには、アダプター クライアントは、関連するリモート関数呼び出し (Rfc)、ビジネス アプリケーション プログラミング インターフェイス (Bapi)、および Idoc (または中間ドキュメント) にアクセスする必要があります。 SAP R/3 システムでは、ビジネスの統合の Rfc、Bapi、Idoc を公開します。 Rfc は、特定のビジネス ロジックを実装するリモート関数モジュールです。 このロジックは、BizTalk Server などの外部アプリケーションまたは .NET アプリケーションから呼び出すことができます。 Bapi は、標準の RFC インターフェイスを通じて公開されるさらに、SAP ビジネス オブジェクトにメソッドのインターフェイスです。 Idoc は、SAP と SAP 以外のシステム間の通信には、電子データ交換 (EDI) 通信レイヤーを抽象化するメカニズムです。 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]Idoc が SAP システムによって公開される、Rfc、Bapi にアクセスすることができます。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]も含まれています[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]、SAP システムへの ADO インターフェイスを提供します。  
  
  このセクションの機能の一覧、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [SAP アダプターの主な機能](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [BizTalk Adapter for mySAP Business Suite の制限事項](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a>参照  
[BizTalk Adapter for mySAP Business Suite の概要します。](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)