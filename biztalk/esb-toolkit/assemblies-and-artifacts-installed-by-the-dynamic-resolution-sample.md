---
title: アセンブリと動的解決サンプルによりインストールされる成果物 |Microsoft Docs
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
ms.openlocfilehash: bc2c8bf9dbf6458c347e0136e49d88a6ee970d24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392284"
---
# <a name="assemblies-and-artifacts-installed-by-the-dynamic-resolution-sample"></a>アセンブリと動的解決サンプルによりインストールされる成果物
次の表は、アセンブリとインストールされている成果物、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決サンプル。  
  
|場所|カテゴリ|コンポーネントの名前とバージョン|  
|--------------|--------------|---------------------------------------|  
|BizTalk アプリケーション GlobalBank.ESB|オーケストレーション|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|送信ポート|DynamicResolutionSolicitResp|  
|||DynamicResolutionOneWay|  
|BizTalk アプリケーション GlobalBank.ESB|受信ポート|DynamicResolutionReqResp|  
|||DynamicResolution|  
|BizTalk アプリケーション GlobalBank.ESB|受信場所|DynamicResolutionReqResp_SOAP<br /><br /> DynamicResolution_FILE|  
|BizTalk アプリケーション GlobalBank.ESB|スキーマ|GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderResponse Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderResponse Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderDoc Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderResponse Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderDoc Version 2.0.0.0|  
|BizTalk アプリケーション GlobalBank.ESB|パイプライン|GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveSendXMLXML バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveXML バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBPassThrough バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|リソース|GlobalBank.ESB.DynamicResolution.Pipelines Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Transforms Version 2.0.0.0|  
|BizTalk アプリケーション GlobalBank.ESB|ポリシー|CanadaSubmitOrderMaps.xml|  
|||GetCanadaEndPoint.xml|  
|||GetCanadaPurchaseEndPoint.xml|  
|||ResolveMap.xml|  
|||ResolveEndPoint.xml|  
|BizTalk アプリケーション GlobalBank.ESB|ボキャブラリ|DynamicRunTimeDocSpecs.xml<br /><br /> DynamicRunTimeEndPoints.xml<br /><br /> DynamicRunTimeMapTypes.xml<br /><br /> DynamicRunTimeServiceActions.xml|  
|BizTalk アプリケーション GlobalBank.ESB|マップ|GlobalBank.ESB.DynamicResolution.Transforms.SubmitPurchaseOrderResponseCN_To_SubmitOrderResponseNA バージョン 2.0.0.0 を =|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN Version=2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitPurchaseOrderRequestCN Version=2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderResponseCN_To_SubmitOrderResponseNA バージョン 2.0.0.0 を =|  
|グローバル アセンブリ キャッシュ|アセンブリ|GlobalBank.ESB.DynamicResolution.Pipelines Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.DynamicResolution.Transforms Version 2.0.0.0|  
|%Program Files %\\BizTalk Server\Pipeline コンポーネント|パイプライン コンポーネント|(なし)|