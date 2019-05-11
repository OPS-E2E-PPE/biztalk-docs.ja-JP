---
title: 手順 7:作成して、ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
- private process tutorial, configuring ports
ms.assetid: c00344c6-506a-4560-a948-e5fed2b9fd58
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 953f616182376b09b3061237b65354d2931db331
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280560"
---
# <a name="step-7-creating-and-configuring-ports"></a>手順 7:作成して、ポートを構成します。
この手順では、作成し、ビジネス プロセスとの通信に使用するポートを構成します。 各ポートは、型、方向、およびバインドのプロパティには。 これらのプロパティは、方向との通信の実行方法と、メッセージが送信または受信されると、どこの場所、通信のパターンを確立します。  
  
### <a name="to-create-a-logical-send-port"></a>論理送信ポートを作成するには  
  
1.  Visual studio で、ツールボックスからドラッグして、**ポート**し、図形をオーケストレーション デザイン画面にドロップ、**ポート画面**を開く、**ポート構成ウィザード**します。  
  
2.  **ポート構成ウィザード**] ページで [**次**します。  
  
3.  **ポートのプロパティ**] ページの [、**名前**ボックスに「 **ContosoSQLReqResponsePort**、順にクリックします**次**します。  
  
4.  **ポートの種類を選択します。** ] ページの [、**ポートの種類名**ボックスに「 **ContosoSQLReqResponsePortName**します。  
  
5.  **通信パターン**、**要求-応答**します。  
  
6.  **アクセス制限**を選択します**内部 - このプロジェクト限定**、順にクリックします**次**します。  
  
7.  **ポートのバインド** ページで、**要求の送信と応答の受信を行います**、ままにして、**ポートのバインド**オプションに設定されて**後で指定**、 をクリックし、**次**します。  
  
8.  をクリックして**完了**ポートを作成します。  
  
### <a name="to-change-the-variable-type-for-the-orchestration-ports"></a>オーケストレーション ポートの変数の型を変更するには  
  
1.  オーケストレーション ビューで、展開**型**、展開**ポートの種類**、展開**ContosoSQLReqResponsePortName**、展開**Operation_1**、選び**要求**します。  
  
2.  [プロパティ] ウィンドウで、選択、**メッセージの種類**プロパティ、展開**スキーマ**順にクリックします**\<参照されたアセンブリから選択\>**.  
  
3.  成果物の種類の選択] ダイアログ ボックスで、[ **ContosoPriceAndAvailability**します。  
  
4.  右側のウィンドウで次のように選択します。 **rootpricerequest**、 をクリックし、 **OK**します。  
  
5.  オーケストレーション ビューで  **Operation_1**、**応答**の**ContosoSQLReqResponsePortName**ポートの種類。  
  
6.  [プロパティ] ウィンドウで、選択、**メッセージの種類**プロパティ、展開**スキーマ**順にクリックします\<**参照されたアセンブリから選択\>**.  
  
7.  **成果物の種類の選択**ダイアログ ボックスで、をクリックして**ContosoPriceAndAvailability**します。  
  
8.  右側のウィンドウで次のように選択します。 **rootPriceResponse**、順にクリックします**OK**します。  
  
### <a name="to-connect-the-ports-to-the-receive-shapes"></a>受信図形にポートに接続するには  
  
1.  オーケストレーション デザイン画面で選択、 **Send_1**図形。  
  
2.  [プロパティ] ウィンドウで、選択、**メッセージ**プロパティ、および選択**Contoso3A2RequestMessage**ドロップダウン リストから。  
  
3.  接続、 **ContosoSQLReqResponsePort**横に緑色のハンドルを選択して、**要求**ラベル上の緑のハンドルにドラッグし、 **Send_1**図形。  
  
4.  オーケストレーション デザイン画面で選択、 **Receive_1**図形。  
  
5.  [プロパティ] ウィンドウで、選択、**メッセージ**プロパティ、および選択 **[contoso3a2responsemessage]** ドロップダウン リストから。  
  
6.  接続、 **ContosoSQLReqResponsePort**横に緑色のハンドルを選択して、**応答**ラベル上の緑のハンドルにドラッグし、 **Receive_1**図形。  
  
7.  **ファイル** メニューのをクリックして**すべて保存**します。  
  
## <a name="see-also"></a>参照  
 [手順 8:Contoso オーケストレーションのビルドと展開](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)