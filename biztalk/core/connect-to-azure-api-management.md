---
title: API Management の SOAP エンドポイントを公開 |Microsoft Docs
description: 使用 Feature Pack 1 と Feature Pack 2 は、BizTalk の Wcf-basic HTTP の公開を API management 内の SOAP エンドポイントと場所が表示されます。 BizTalk 管理コンソールを使用して実行したり、Azure portal で API Management 内で直接、エンドポイントを貼り付けます。
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: 2
author: MandiOhlinger
ms.author: valrobb
manager: anneta
ms.openlocfilehash: c8bdb3cb3f2d0fc247ea607a1b34623006315754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993715"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a>API Management での BizTalk SOAP エンドポイントを公開します。

Azure API Management 内のサービスと、BizTalk SOAP エンドポイントを公開します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 1**、BizTalk から API Management で SOAP エンドポイントを公開することができます。 Azure portal で API Management を使用してこれが実行できます。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**Wcf-basichttp を公開する BizTalk 管理コンソールを使用して Azure API Management 内のエンドポイントと場所を受信します。 

> [!TIP]
> [API Management とは何ですか。](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)優れたリソースを理解し、この Azure サービスの詳細について説明します。

## <a name="prerequisites"></a>前提条件
* 構成およびセットアップ[Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)
* 作成、[仮想ネットワーク](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet)BizTalk コンピューターと API Management インスタンスの間
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)を BizTalk Server

## <a name="create-using-api-management-in-azure-portal"></a>Azure portal で API Management を使用して作成します。 
1. [Azure portal](https://portal.azure.com)を開いて、API management を選択します**Api**:

    ![BizTalk の API を選択します。](../core/media/select-api-for-biztalk.png)
    
2. 選択**WSDL**:

    ![選択 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. WSDL のプロパティを構成します。 

   1. **WSDL 仕様**: BizTalk SOAP エンドポイントに完全な URI を入力します。 たとえば、ように入力します`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`または`http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`します。  

   2. **SOAP パススルー**または**SOAP REST から**: 設定を選択します。 
       * **SOAP REST から**: 既存の (SOAP) ベースの web サービスからの HTTP Api の作成 (REST) ベース
       * **SOAP パススルー**: SOAP API のプロキシとして機能します。 

   3. 優先入力**表示名**、**名前**、**説明**、 **API Url サフィックス**、**製品**、**バージョン**します。

      完了したら、WSDL 構成が、次のようになります。 

      ![BizTalk の WSDL から API を作成します。](../core/media/create-api-from-wsdl-biztalk.png)

4. **[作成]** を選択します。

## <a name="create-using-the-biztalk-administration"></a>BizTalk 管理コンソールを使用して作成します。

> [!NOTE] 
> この機能をサポートする、Wcf-basichttp 受信場所。 

1. BizTalk 管理コンソールで、Wcf-basichttp 受信場所、および選択を右クリック**API Management に公開**:  

    ![[発行] メニュー オプション](../core/media/publish-to-api-management-option.png)
 
2. API 管理のプロパティを構成します。 

   1. **サインイン**、Azure サブスクリプションを選択して、**サブスクリプション**と**リソース グループ**を持つ API management サービスであり、サービスを選択します。

   2. **WSDL 仕様リンク**WSDL ファイルが自動的に設定されます。 置換**localhost** DNS 名または BizTalk Server の IP アドレス。 

   3. 選択**SOAP パススルー**または**SOAP REST から**:  
      * **SOAP REST から**: 既存の SOAP ベースの web サービスからの HTTP Api の作成 (REST) ベース
      * **SOAP パススルー**: SOAP API のプロキシとして機能します。 

        API 発行する両方の方法を変更して、 **API URL サフィックス**、し、さまざまな API の種類を使用して、発行します。

   4. **API 名**受信場所の名前が自動的に設定されます。

   5. 選択、 **API URL サフィックス**API のコンシューマーによって使用されます。 

      完了したらのプロパティは、次のようになります。  
      ![API ウィンドウへの公開します。](../core/media/api-management-publish-window.png)


3. 選択**発行**します。 内の API Management でサービスとして、受信場所が表示されます、成功すると、 [Azure portal](https://portal.azure.com)します。 

## <a name="do-more"></a>さらに活用します。
Azure API Management は、Logic Apps などの Azure サービスの多くで使用される強力なサービスです。 API Management には、多くの機能、転送率の制限およびクォータは、独自の Api にアクセスできるユーザーを含む、キャッシュ、および詳細が含まれています。 参照してください[API Management とは何ですか?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)を開始します。

## <a name="see-also"></a>参照
[Feature Pack の構成](configure-the-feature-pack.md)
