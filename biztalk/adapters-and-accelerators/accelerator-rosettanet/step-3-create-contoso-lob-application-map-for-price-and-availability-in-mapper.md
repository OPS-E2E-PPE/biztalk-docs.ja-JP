---
title: 手順 3:Price and Availability プロジェクトを使用して BizTalk マッパーの Contoso LOB アプリケーションを作成するマップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d7a1289bc11517e97bac706803ad0c78dbc2d5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281152"
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a>手順 3:Price and Availability プロジェクトの BizTalk マッパーを使用して用の Contoso LOB アプリケーション マップを作成します。
この手順では、2 つの取引先間でメッセージを正常に交換するために必要な変換を定義する 2 つのマップを作成します。 このシナリオで、Contoso ERP システムが Price and Availability 要求のメッセージ形式に標準化されています。 2 つのマップは、Fabrikam 取引先からの要求および応答メッセージ、内部的に定義された Contoso のメッセージを送受信するそれぞれマップします。  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a>3 a 2 PriceAndAvailability Request スキーマの参照を追加するには  
  
1.  ソリューション エクスプ ローラーで [contosopriceandavailability] プロジェクトを右クリックし、クリックして**参照の追加**します。  
  
2.  [参照の追加] ダイアログ ボックスで、**参照**します。  
  
3.  フォルダーに移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin を選択し、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**アセンブリ。  
  
4.  クリックして**追加**、順にクリックします**OK**します。  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a>Contoso の PriceAndAvailability 要求へのマップを 3 a 2 PriceAndAvailability 要求を作成するには  
  
1.  ソリューション エクスプ ローラーで、contosopriceandavailability プロジェクトを右クリックして**追加**、 をクリックし、**新しい項目の**します。  
  
2.  新しい項目の追加 - ContosoPriceAndAvailability ダイアログ ボックスでは、次のように選択します。**マップ ファイル**カテゴリ ウィンドウで選択し**マップ**で、**テンプレート**ウィンドウ。 **名前**ボックスに「 **PIP3A2RequestToContosoPriceRequest**、 をクリックし、**追加**します。  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a>PIP3A2RequestToContosoPriceRequest マップのスキーマを関連付ける  
  
1.  (Pip3a2requesttocontosopricerequest.btm が表示されます)、BizTalk マッパーで、送信元スキーマ ペインで次のようにクリックします。**ソース スキーマを開く**します。  
  
2.  BizTalk 型の選択 ダイアログ ボックスで、 **ContosoPriceAndAvailability**、展開**参照**、展開**microsoft.solutions.btarn.schemas.rnpips**、し、展開**スキーマ。**  
  
3.  選択 **[microsoft.solutions.btarn.schemas.rnpips]。**  
  
     **_ 3 a2priceandavailabilityquerymessageguideline_v1_3**、 をクリックし、 **OK**します。  
  
4.  送信先スキーマ ペインで次のようにクリックします。**送信先スキーマを開く**します。  
  
5.  BizTalk 型の選択 ダイアログ ボックスで、 **ContosoPriceAndAvailability**、順に展開**スキーマ**します。  
  
6.  選択、 **ContosoPriceAndAvailability.ContosoPriceSchema**スキーマ、およびクリック**OK**します。  
  
7.  ターゲット スキーマ ダイアログ ボックスの ルート ノードで選択、 **rootpricerequest**スキーマ、およびクリック**OK**します。  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a>PIP3A2RequestToContosoPriceRequest マップのスキーマのフィールドをリンクするには  
  
1.  送信先スキーマ ペインで右クリックし、 **\<スキーマ\>** ノードをクリック**ツリー ノードの展開**します。  
  
2.  送信元スキーマ ペインで右クリックし、 **\<スキーマ\>** ノードをクリック**ツリー ノードの展開**します。  
  
3.  ドラッグ、 **GlobalProductIdentifier**フィールドを**ProductID**送信先スキーマ ペインでフィールド。  
  
    > [!NOTE]
    >  検索することができます、 **GlobalProductIdentifier**フィールドには、pip3a2priceandavailabilityquery/productpriceandavailabilityquery/  
    >   
    >  ProductPriceAndAvailability/ProductLineItem/productUnit/  
    >   
    >  ProductPackageDescription あります。  
  
4.  **ファイル** メニューのをクリックして**すべて保存**変更を保存します。  
  
## <a name="see-also"></a>参照  
 [Contoso の BizTalk ポートの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)