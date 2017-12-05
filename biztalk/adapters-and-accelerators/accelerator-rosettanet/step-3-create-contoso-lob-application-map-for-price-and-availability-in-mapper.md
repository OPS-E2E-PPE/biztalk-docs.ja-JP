---
title: "手順 3: Price and Availability プロジェクトを使用して BizTalk マッパーの Contoso LOB アプリケーションの作成はマップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fef0f6e951798dd2453aa387d8dcde9853968f3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a>手順 3: Price and Availability プロジェクトの BizTalk マッパーを使用して用の Contoso LOB アプリケーション マップの作成
ここでは、2 つのマップを作成します。このマップは 2 つの取引先間でメッセージを正常に交換するために必要な変換を定義します。 このシナリオでは、Contoso ERP システムは Price and Availability Request のメッセージ形式を既に標準化しています。 2 つのマップは、取引先である Fabrikam からの要求メッセージと応答メッセージを、内部的に定義された Contoso のメッセージにそれぞれマップします。  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a>3A2 PriceAndAvailability Request スキーマの参照を追加するには  
  
1.  ソリューション エクスプ ローラーで、[contosopriceandavailability] プロジェクトを右クリックし、をクリックして**参照の追加**です。  
  
2.  [参照の追加] ダイアログ ボックスで、**参照**です。  
  
3.  フォルダーに移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin し、選択、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**アセンブリ。  
  
4.  をクリックして**追加**、順にクリック**OK**です。  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a>3A2 PriceAndAvailability 要求から Contoso PriceAndAvailability 要求へのマップを作成するには  
  
1.  ソリューション エクスプ ローラーで、contosopriceandavailability プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**です。  
  
2.  新しい項目の追加 - ContosoPriceAndAvailability ダイアログ ボックスで選択**マップ ファイル**カテゴリ ウィンドウで、選択**マップ**で、**テンプレート**ウィンドウです。 **名前**ボックスに、入力**PIP3A2RequestToContosoPriceRequest**、クリックして**追加**です。  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a>PIP3A2RequestToContosoPriceRequest マップのスキーマを関連付けるには  
  
1.  (Pip3a2requesttocontosopricerequest.btm が表示されます)、BizTalk マッパーで送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
2.  BizTalk 型の選択 ダイアログ ボックスで、展開**ContosoPriceAndAvailability**、展開**参照**、展開**Microsoft.Solutions.BTARN.Schemas.RNPIPs**、し、展開**スキーマです。**  
  
3.  選択**Microsoft.Solutions.BTARN.Schemas.RNPIPs です。**  
  
     **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**、クリックして**OK**です。  
  
4.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
5.  BizTalk 型の選択 ダイアログ ボックスで、展開**ContosoPriceAndAvailability**、順に展開**スキーマ**です。  
  
6.  選択、 **ContosoPriceAndAvailability.ContosoPriceSchema**スキーマ、およびクリック**OK**です。  
  
7.  ターゲット スキーマ ダイアログ ボックスのルート ノードで、選択、 **rootPriceRequest**スキーマ、およびクリック**OK**です。  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a>PIP3A2RequestToContosoPriceRequest マップのスキーマ フィールドをリンクするには  
  
1.  送信先スキーマ ペインで右クリックし、 **\<スキーマ\>**ノードをクリックして**ツリー ノードの展開**です。  
  
2.  送信元スキーマ ペインで右クリックし、 **\<スキーマ\>**ノードをクリックして**ツリー ノードの展開**です。  
  
3.  ドラッグ、 **GlobalProductIdentifier**フィールドを**ProductID**送信先スキーマ ペインでフィールドです。  
  
    > [!NOTE]
    >  検索することができます、 **GlobalProductIdentifier**フィールドで、pip3a2priceandavailabilityquery/productpriceandavailabilityquery/  
    >   
    >  ProductPriceAndAvailability/ProductLineItem/productUnit/  
    >   
    >  ProductPackageDescription/ProductIdentification ノードにあります。  
  
4.  **ファイル** メニューのをクリックして**すべて保存**して変更を保存します。  
  
## <a name="see-also"></a>参照  
 [Contoso の BizTalk ポートの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)