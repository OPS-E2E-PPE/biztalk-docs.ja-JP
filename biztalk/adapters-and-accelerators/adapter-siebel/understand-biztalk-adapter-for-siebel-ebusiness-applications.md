---
title: "Siebel eBusiness Applications の BizTalk アダプターを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad8aecf0faa0a9a0117feaf91e5fa91203fa63f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a>Siebel eBusiness Applications の BizTalk アダプターを理解します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]外部システムと対話するためにサービス指向のプログラムによるアクセスを有効にします。 アダプターでは、次の利点をクライアントに使用します。  
  
-   **デザイン時のエクスペリエンスを一貫した**です。 アダプターは、参照、検索、および LOB アーティファクトのメタデータを取得するための一般的なとわかりやすいデザイン時のエクスペリエンスを提供します。  
  
-   **さまざまなプログラミング オプション**です。 アダプターは、Windows Communication Foundation (WCF) などのプログラミング モデルの選択肢を提供するチャネル モデルを WCF サービス モデルでは、ADO.NET、Web サービス、または BizTalk は、モデルをサポートします。  
  
-   **Lob の間でのエクスペリエンス、統一された**です。 使用して、WCF アダプターを標準化および[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]でき、したがって一貫した環境での任意の LOB システムへのアクセスを取得します。  
  
 前述のように、アダプターは、上に組み込ま、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]です。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]のさまざまな BizTalk Server および Microsoft Office などのクライアント アプリケーションで使用できる統合アダプターを構築するための共通の基本を提供します。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が Windows Communication Foundation (WCF) チャネルとの統合アダプターを公開することにより、アダプター戦略の Microsoft サービスの戦略を揃えて配置します。 詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ドキュメント。 と共に、ドキュメントがインストールされている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通常 \<インストール ドライブ >: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents です。  
  
 Siebel システムでの操作を行うには、Siebel システムによって公開されるビジネス サービスへのアクセスがアダプターのクライアントに必要です。 Siebel アプリケーションでは、ビジネス コンポーネントとビジネス オブジェクト データを公開します。 Siebel*ビジネス コンポーネント*を 1 つの構造に 1 つまたは複数のテーブルの列を関連付ける論理エンティティです。 Siebel*ビジネス オブジェクト*一連の相互に関連するビジネス コンポーネントの連携により、ビジネス モデルを実装します。 [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]アダプターのクライアントは、Siebel ビジネス オブジェクトとビジネス コンポーネントを表示できます。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]も含まれています、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET インターフェイスを拡張することによって、Siebel システムへの ADO インターフェイスを提供します。  
  
 このセクションでの機能について説明します、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk adapter 用 Siebel eBusiness Applications の概要](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Siebel アダプターの主要な機能](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [BizTalk adapter 用 Siebel eBusiness Applications の制限事項](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Data Provider 用 Siebel について](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)