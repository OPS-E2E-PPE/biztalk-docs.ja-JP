---
title: チュートリアル 1:SharePoint サイト上の SAP システムからのデータ表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5365f75982677124e8cd529ffa78b76c66dd2358
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372398"
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a>チュートリアル 1:SharePoint サイト上の SAP システムからデータを表示します。
このチュートリアルを使用して詳細な手順では、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SharePoint ポータルでの SAP システムからビジネス データを表示する Microsoft Office SharePoint Server を使用します。 使用する方法を示すために、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint server では、ビジネスでの 2 つの最も一般的なエンティティ検討してください: 顧客および販売注文します。 この例では、Office SharePoint Server を使用して、アプリケーションを作成、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以下を実行します。  
  
- 検索文字列に基づいて、SAP システムから顧客の一覧を取得します。  
  
- 顧客の一覧と表示の詳細から顧客を選択します。  
  
- 選択した顧客の販売注文を取得します。  
  
  SAP システムから顧客データを抽出するには、SD_RFC_CUSTOMER_GET RFC を使用します。 特定の顧客の販売注文に関する情報を抽出するには、BAPI_SALESORDER_GETLIST RFC を使用します。  
  
> [!NOTE]
>  SAP システムの一部のバージョンでは、SD_RFC_CUSTOMER_GET ではなく RFC_CUSTOMER_GET RFC を公開します。  
> 
> [!NOTE]
>  このチュートリアルで前を使用するためのすべての前提条件がインストールされているを確認します、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Office SharePoint Server の使用。 前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイド、通常は c:/プログラム ファイルまたは Microsoft にインストールされている [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] /文書化します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: SAP アイテムを WCF サービスとして公開する](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [手順 2:SAP アイテム用のアプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [ステップ 3:SAP からデータを取得するための SharePoint アプリケーションを作成する](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [手順 4:SharePoint アプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプター チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)