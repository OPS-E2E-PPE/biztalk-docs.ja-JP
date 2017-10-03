---
title: "MySAP Business Suite の BizTalk アダプターを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 359bbc9d25465cf5c293d24a12ffeb698b11ab02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a>MySAP Business Suite の BizTalk アダプターを理解します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを有効にします。 アダプターでは、次の利点をクライアントに使用します。  
  
-   **デザイン時のエクスペリエンスを一貫した**です。 アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的なとわかりやすいデザイン時のエクスペリエンスを提供します。  
  
-   **さまざまなプログラミング オプション**です。 アダプターは、プログラミング モデル Windows Communication Foundation (WCF) チャネル モデルを含む、WCF サービスのモデル、ADO.NET、web サービス、またはサポートされている BizTalk モデルの選択肢を提供します。  
  
-   **Lob の間でのエクスペリエンス、統一された**です。 使用して、WCF アダプターを標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。  
  
 前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]のさまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本を提供します。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が Windows Communication Foundation (WCF) チャネルとの統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。 詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。 と共に、ドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常 \<インストール ドライブ >: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。  
  
 SAP システムに対して操作を実行するには、アダプターのクライアントは、関連するリモート関数呼び出し (Rfc)、ビジネス アプリケーション プログラミング インターフェイス (Bapi) と Idoc (中級者向けのドキュメント) へのアクセスが必要です。 SAP R/3 システムは、ビジネスの統合の Rfc、Bapi、および Idoc を公開します。 Rfc は、特定のビジネス ロジックを実装しているリモート関数モジュールです。 このロジックは、BizTalk Server など、外部アプリケーションまたは .NET アプリケーションから呼び出すことができます。 Bapi は、標準の RFC インターフェイスを介して公開されるさらに、SAP ビジネス オブジェクトをメソッドのインターフェイスです。 Idoc は、SAP および SAP 以外のシステム間の通信には、電子データ交換 (EDI) 通信レイヤーを抽象化するメカニズムです。 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]Idoc が SAP システムによって公開される、Rfc、Bapi にアクセスすることができます。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]も含まれています[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]、SAP システムの ADO インターフェイスを提供します。  
  
 このセクションの機能の一覧、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [SAP アダプターの主要な機能](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [BizTalk adapter 用 mySAP Business Suite の制限事項](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [.NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a>参照  
[BizTalk Adapter 用 mySAP Business Suite の概要します。](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)