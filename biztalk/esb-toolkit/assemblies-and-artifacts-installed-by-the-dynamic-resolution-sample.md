---
title: アセンブリと動的な解決サンプルがインストールされている成果物 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d9ffdc4-1721-4202-839c-04e5bffe8668
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee337b56c6e0901de6b02b28df69101ad3aaf3ff
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006995"
---
# <a name="assemblies-and-artifacts-installed-by-the-dynamic-resolution-sample"></a>アセンブリと動的な解決サンプルがインストールされている成果物
次の表は、アセンブリおよびによってインストールされているアイテム、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決のサンプルです。  
  
|場所|カテゴリ|コンポーネントの名前とバージョン|  
|--------------|--------------|---------------------------------------|  
|BizTalk アプリケーション GlobalBank.ESB|オーケストレーション|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|送信ポート|DynamicResolutionSolicitResp|  
|||DynamicResolutionOneWay|  
|BizTalk アプリケーション GlobalBank.ESB|受信ポート|DynamicResolutionReqResp|  
|||DynamicResolution|  
|BizTalk アプリケーション GlobalBank.ESB|受信場所|DynamicResolutionReqResp_SOAP<br /><br /> DynamicResolution_FILE|  
|BizTalk アプリケーション GlobalBank.ESB|スキーマ|GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderResponse バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderResponse バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderDoc バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderResponse バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderDoc バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|パイプライン|GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveSendXMLXML バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveXML バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBPassThrough バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|リソース|GlobalBank.ESB.DynamicResolution.Pipelines バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Schemas バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Transforms バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|ポリシー|CanadaSubmitOrderMaps.xml|  
|||GetCanadaEndPoint.xml|  
|||GetCanadaPurchaseEndPoint.xml|  
|||ResolveMap.xml|  
|||ResolveEndPoint.xml|  
|BizTalk アプリケーション GlobalBank.ESB|ボキャブラリ|DynamicRunTimeDocSpecs.xml<br /><br /> DynamicRunTimeEndPoints.xml<br /><br /> DynamicRunTimeMapTypes.xml<br /><br /> DynamicRunTimeServiceActions.xml|  
|BizTalk アプリケーション GlobalBank.ESB|マップ|GlobalBank.ESB.DynamicResolution.Transforms.SubmitPurchaseOrderResponseCN_To_SubmitOrderResponseNA バージョン 2.0.0.0 を =|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN バージョン 2.0.0.0 を =|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitPurchaseOrderRequestCN バージョン 2.0.0.0 を =|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderResponseCN_To_SubmitOrderResponseNA バージョン 2.0.0.0 を =|  
|グローバル アセンブリ キャッシュ|アセンブリ|GlobalBank.ESB.DynamicResolution.Pipelines バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Schemas バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Transforms バージョン 2.0.0.0 以降|  
|%Program Files %\\BizTalk Server\Pipeline コンポーネント|パイプライン コンポーネント|(なし)|