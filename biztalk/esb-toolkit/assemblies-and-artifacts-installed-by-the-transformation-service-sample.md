---
title: アセンブリと、変換サービス サンプルによりインストールされる成果物 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 890c089a-749e-421f-a6eb-2e038cd2122e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f7806725282a3e37bcd9d4686585577afa94515
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392109"
---
# <a name="assemblies-and-artifacts-installed-by-the-transformation-service-sample"></a>アセンブリと、変換サービス サンプルによりインストールされる成果物
次の表は、アセンブリとインストールされている成果物、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]変換サービス サンプル。  
  
|場所|カテゴリ|コンポーネントの名前とバージョン|  
|--------------|--------------|---------------------------------------|  
|BizTalk アプリケーション GlobalBank.ESB|オーケストレーション|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|送信ポート|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|受信ポート|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|受信場所|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|スキーマ|GlobalBank.ESB.TransformServices.Schemas.RetailOrder バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.TransformServices.Schemas.OrderConfirmation バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.TransformServices.Schemas.CanonicalOrder バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|パイプライン|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|リソース|GlobalBank.ESB.TransformServices.Maps バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.TransformServices.Schemas バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|ポリシー|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|マップ|GlobalBank.ESB.TransformServices.Maps.CanonicalOrder_To_OrderConfirmation バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.TransformServices.Maps.RetailOrder_To_CanonicalOrder バージョン 2.0.0.0 以降|  
|グローバル アセンブリ キャッシュ|アセンブリ|GlobalBank.ESB.TransformServices.Maps バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.TransformServices.Schemas バージョン 2.0.0.0 以降|  
|%Program Files %\\BizTalk Server\Pipeline コンポーネント|パイプライン コンポーネント|(なし)|