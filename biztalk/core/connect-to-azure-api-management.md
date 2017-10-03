---
title: "BizTalk Server を使用して Azure API Management への接続 |Microsoft ドキュメント"
description: "BizTalk 機能パック 1 を使用して、BizTalk Server から API management に接続するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: "2"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d0c5e4cd2a0ebbd7108845ea15de468d0e0a5a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-azure-api-management"></a>Azure API Management への接続します。
ここで BizTalk から API 管理により、SOAP エンドポイントを簡単に公開できます。

## <a name="what-is-azure-api-management"></a>Azure API Management とは
内部および外部の顧客に Api を公開するため、ターンキー ソリューションとして Azure API Management を使用します。 一貫性をすばやく作成し、どこにでもホストされている既存のバックエンド サービスの最新の API ゲートウェイをセキュリティで保護使いすぎ、不正使用から保護すると、使用状況と正常性に関する洞察を取得します。 さらに、自動化し、API プログラムを準備して稼働させるために、開発者のオンボーディングを拡張します。 

参照してください[API Management](https://azure.microsoft.com/en-us/services/api-management/)を API Management の詳細を参照してください。

## <a name="prerequisites"></a>前提条件
* 構成およびセットアップ[Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)
* 作成、[仮想ネットワーク](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet)BizTalk コンピューターと API 管理インスタンス間で


1. Azure ポータルで、API management を開き、選択**Api**  メニューから。

    ![BizTalk の API を選択します。](../core/media/select-api-for-biztalk.png)
    
2. オプションを選択**WSDL**新しい API セクション。

    ![選択 wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. BizTalk の WSDL に API Management に接続するには、SOAP エンドポイントへの完全 URI での BizTalk コンピューターに対する URL をコピーします。 たとえば、コピー `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:

    ![WSDL BizTalk から API を作成します。](../core/media/create-api-from-wsdl-biztalk.png)

4. 使用する場合に選択、 **SOAP パススルー**、設定、または、**他の部分 SOAP**サービス。
5. 入力してください、**名前**、API の**説明**、および**API Url サフィックス**サービス用です。
6. 選択**作成**バックエンドの SOAP エンドポイントへの通信を作成します。

## <a name="see-also"></a>参照
[Feature Pack の構成](configure-the-feature-pack.md)