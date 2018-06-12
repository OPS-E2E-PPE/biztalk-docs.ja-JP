---
title: API Management の SOAP エンドポイントを公開 |Microsoft ドキュメント
description: BizTalk Wcf-basic HTTP を公開するには、使用する機能パック 1 および Feature Pack 2 は、API management 内で SOAP エンドポイントと場所を受信します。 BizTalk 管理コンソールを使用してこれを行うか、Azure ポータルで API Management 内で直接、エンドポイントを貼り付けますことができます。
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
ms.openlocfilehash: eb716729dcdbac07c5b17cf267866cf282046a70
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848954"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a>API Management で BizTalk SOAP エンドポイントを公開します。

Azure API Management 内でサービスとして、BizTalk SOAP エンドポイントを公開します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]機能パック 1**、API Management BizTalk からによって SOAP エンドポイントを公開することができます。 これを行う、Azure ポータルで API Management を使用します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**Wcf-basichttp を公開する BizTalk 管理コンソールを使用して Azure API Management 内のエンドポイントと場所を受信します。 

> [!TIP]
> [API Management とは何ですか。](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)を理解し、Azure サービスに関する詳細については、優れたリソースです。

## <a name="prerequisites"></a>前提条件
* 構成およびセットアップ[Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)
* 作成、[仮想ネットワーク](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet)BizTalk コンピューターと、API Management インスタンス間で
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2) BizTalk Server で

## <a name="create-using-api-management-in-azure-portal"></a>Azure ポータルで API Management を使用して作成します。 
1. [Azure ポータル](https://portal.azure.com)、API 管理を開くし、選択、 **Api**:

    ![BizTalk の API を選択します。](../core/media/select-api-for-biztalk.png)
    
2. 選択**WSDL**:

    ![選択 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. WSDL のプロパティを構成します。 

    1. **WSDL 仕様**: から BizTalk SOAP エンドポイントへの完全 URI を入力します。 たとえば、ように入力`http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`または`http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`です。  

    2. **SOAP パススルー**または**他の部分 SOAP** : 設定を選択します。 
        * **他の部分 SOAP**: 既存の SOAP ベースの web サービスからの HTTP Api の作成 (REST) ベース
        * **SOAP パススルー**: SOAP API のプロキシとして機能 

    3. 優先入力**表示名**、**名前**、**説明**、 **API Url サフィックス**、**製品**、および**バージョン**します。

    完了したら、WSDL 構成のようになります次。 

    ![WSDL BizTalk から API を作成します。](../core/media/create-api-from-wsdl-biztalk.png)

4. **[作成]** を選択します。

## <a name="create-using-the-biztalk-administration"></a>BizTalk 管理コンソールを使用して作成します。

> [!NOTE] 
> この機能をサポートする、Wcf-basichttp 受信場所。 

1. BizTalk 管理コンソールで、右クリックして、Wcf-basichttp 受信場所、および選択**API Management に発行**:  

    ![パブリッシュ メニュー オプション](../core/media/publish-to-api-management-option.png)
 
2. API 管理のプロパティを構成します。 

    1. **サイン イン**、Azure サブスクリプションを選択して、**サブスクリプション**と**リソース グループ**を持つ、API management サービスであり、サービスを選択します。

    2. **WSDL 仕様リンク**WSDL ファイルが自動的に表示されます。 置き換える**localhost** DNS 名または BizTalk Server の IP アドレスでします。 

    3. 選択**SOAP パススルー**または**他の部分 SOAP**:  
        * **他の部分 SOAP**: 既存の SOAP ベースの web サービスからの HTTP Api の作成 (REST) ベース
        * **SOAP パススルー**: SOAP API のプロキシとして機能 

        API によって発行できます両方の方法を変更する、 **API URL サフィックス**、し、これは、各種の API を使ってもう一度発行します。

    4. **API 名**受信場所の名前が自動的に表示されます。

    5. 選択、 **API URL サフィックス**API のコンシューマーによって使用されることができます。 

    完了したらのプロパティが、次のようになります。  
    ![API ウィンドウへの公開します。](../core/media/api-management-publish-window.png)


3. 選択**発行**です。 成功すると、受信場所が表示されますで API Management でサービスとして、 [Azure ポータル](https://portal.azure.com)です。 

## <a name="do-more"></a>複数の操作を行います
Azure API Management とは、多数の Logic Apps を含む、Azure のサービスによって使用される強力なサービスです。 API Management には、多くの機能、転送率の制限、クォータ、独自の Api へのアクセスを持つなど、キャッシュ、および詳細が含まれています。 参照してください[API Management は何ですか?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)作業を開始します。

## <a name="see-also"></a>参照
[Feature Pack の構成](configure-the-feature-pack.md)
