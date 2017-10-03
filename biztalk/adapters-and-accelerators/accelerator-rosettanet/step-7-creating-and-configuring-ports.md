---
title: "手順 7: を作成して、ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
- private process tutorial, configuring ports
ms.assetid: c00344c6-506a-4560-a948-e5fed2b9fd58
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c93f7c07f92c7517dbc84403747da869e0d4ceb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-creating-and-configuring-ports"></a>手順 7: を作成して、ポートを構成します。
ここでは、ビジネス プロセスとの通信に使用するポートを作成し、構成します。 各ポートには、種類、方向、およびバインドのプロパティを設定します。 これらのプロパティにより、通信の方向と通信方式、メッセージの送信先と受信元、および通信の実行方法が決定されます。  
  
### <a name="to-create-a-logical-send-port"></a>論理送信ポートを作成するには  
  
1.  Visual Studio で、ツールボックスからドラッグして、**ポート**図形をオーケストレーション デザイン画面にし、上にドロップ、**ポート画面**を開くには、**ポート構成ウィザード**です。  
  
2.  **ポート構成ウィザード**] ページで [**次**です。  
  
3.  **ポートのプロパティ**] ページの [、**名前**ボックスに、入力**ContosoSQLReqResponsePort**、クリックして**[次へ]**です。  
  
4.  **ポートの種類を選択して**] ページの [、**ポートの種類名**ボックスに、入力**ContosoSQLReqResponsePortName**です。  
  
5.  **通信パターン****要求-応答**です。  
  
6.  **アクセス制限****内部 - このプロジェクト限定**、順にクリック**次へ**です。  
  
7.  **ポートのバインド** ページで、**要求の送信と応答の受信を行います**のままにして、**ポートのバインド**オプションに設定**後で**、クリックして**次**です。  
  
8.  をクリックして**完了**ポートを作成します。  
  
### <a name="to-change-the-variable-type-for-the-orchestration-ports"></a>オーケストレーション ポートに関するさまざまな種類を変更するには  
  
1.  オーケストレーション ビューで、展開**型**、展開**ポートの種類**、展開**ContosoSQLReqResponsePortName**、展開**Operation_1**、クリックして**要求**です。  
  
2.  プロパティ ウィンドウで、選択、**メッセージの種類**プロパティ、展開**スキーマ** をクリックし、 **\<参照されたアセンブリから選択 >**です。  
  
3.  成果物の種類の選択 ダイアログ ボックスで、をクリックして**ContosoPriceAndAvailability**です。  
  
4.  右側のペインで選択**rootPriceRequest**、順にクリック**OK**です。  
  
5.  オーケストレーション ビューで、 **operation_1****応答**の**ContosoSQLReqResponsePortName**ポートの種類。  
  
6.  プロパティ ウィンドウで、選択、**メッセージの種類**プロパティ、展開**スキーマ** をクリックし、 \<**参照されたアセンブリから選択 >**です。  
  
7.  **成果物の種類の選択**ダイアログ ボックスで、をクリックして**ContosoPriceAndAvailability**です。  
  
8.  右側のペインで選択**[rootpriceresponse]**、順にクリック**OK**です。  
  
### <a name="to-connect-the-ports-to-the-receive-shapes"></a>受信側の図形にポートを接続するには  
  
1.  オーケストレーション デザイン画面で選択、 **Send_1**図形です。  
  
2.  [プロパティ] ウィンドウで、選択、**メッセージ**プロパティ、および選択**Contoso3A2RequestMessage**ドロップダウン リストからです。  
  
3.  接続、 **ContosoSQLReqResponsePort**を横に緑色のハンドルを選択すると、**要求**ラベル上の緑のハンドルにドラッグし、 **Send_1**図形です。  
  
4.  オーケストレーション デザイン画面で選択、 **Receive_1**図形です。  
  
5.  [プロパティ] ウィンドウで、選択、**メッセージ**プロパティ、および選択**[contoso3a2responsemessage]**ドロップダウン リストからです。  
  
6.  接続、 **ContosoSQLReqResponsePort**を横に緑色のハンドルを選択すると、**応答**ラベル上の緑のハンドルにドラッグし、 **Receive_1**図形です。  
  
7.  **ファイル** メニューのをクリックして**すべて保存**です。  
  
## <a name="see-also"></a>参照  
 [手順 8: ビルドと Contoso オーケストレーションの展開](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)