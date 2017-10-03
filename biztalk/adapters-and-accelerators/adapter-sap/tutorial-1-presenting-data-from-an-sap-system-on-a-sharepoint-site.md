---
title: "チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdc3ea5e41600aebcef1fda933735c418dec78c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a>チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示
このチュートリアルを使用して詳細な手順を説明する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Microsoft Office SharePoint Server、SharePoint portal に SAP システムからビジネス データを表示するとします。 使用する方法を示すために、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint Server と、あらゆるビジネスで 2 つの最も一般的なエンティティを考慮します: 顧客および販売注文します。 Office SharePoint server を使用してアプリケーションを作成するこの例では、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を次を行うには。  
  
-   検索文字列に基づき、SAP システムから顧客の一覧を取得します。  
  
-   顧客のリストと存在詳細から顧客を選択します。  
  
-   選択した顧客の販売注文を取得します。  
  
 SAP システムから顧客データを抽出するには、SD_RFC_CUSTOMER_GET RFC を使用します。 特定の顧客の販売注文に関する情報を抽出するには、BAPI_SALESORDER_GETLIST RFC を使用します。  
  
> [!NOTE]
>  SAP システムのバージョンによっては、SD_RFC_CUSTOMER_GET ではなく RFC_CUSTOMER_GET RFC を公開します。  
  
> [!NOTE]
>  チュートリアルの前を使用するためのすべての前提条件がインストールされていることを確認してください、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint Server とします。 前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]通常 c:/program ファイルまたは Microsoft にインストールされているインストール ガイド[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]ドキュメント/です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: WCF サービスとして SAP アイテムを公開します。](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成します。](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [手順 3: SAP からデータを取得する SharePoint アプリケーションを作成します。](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [手順 4: SharePoint アプリケーションをテストします。](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)