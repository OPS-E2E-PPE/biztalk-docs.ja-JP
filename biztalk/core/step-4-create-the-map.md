---
title: 手順 4:マップを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f7f1f6d-0e57-4a65-b91d-c81fcc832961
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cf9def7682b9334af451b5230cc2790fb7a6021
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392543"
---
# <a name="step-4-create-the-map"></a>手順 4:マップを作成します。
![手順 4. 5 の](../core/media/step-4of5.gif "Step_4of5")  
  
 **所要時間:** 6 分  
  
 **目標:** この手順では、要求メッセージを RequestDecline メッセージに変換するマップを作成します。  
  
 **目的:** マップにより、要求の ID 番号と総計を倉庫在庫システムに返される要求拒否メッセージに含まれること。 送信メッセージに対して定義されたフィールドに、受信メッセージ内のフィールドをリンクするのにには、BizTalk マッパーを使用します。 これは、機能は、これら 2 つのメッセージには、同じスキーマ構造があるないため必要です。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 2。在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)と[手順 3。要求拒否スキーマの作成](../core/step-3-create-the-request-decline-schema.md)です。  
  
## <a name="procedures"></a>手順  
 マップは、要求スキーマと RequestDecline スキーマに依存します。  はるか、マップで使用するには、スキーマを使用してプロジェクトをコンパイルします。  
  
#### <a name="to-compile-the-eaischemas-project"></a>EAISchemas プロジェクトをコンパイルするには  
  
-   ソリューション エクスプ ローラーで右クリックして**EAISchemas**、 をクリックし、**ビルド**します。  
  
#### <a name="to-create-the-map"></a>マップを作成するには、次の操作を行います。  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  
  
2.  **新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストール済みテンプレート**|クリックして**マップ ファイル**、 をクリックし、**マップ**します。|  
    |**名前**|型**MapToReqDecline.btm**します。|  
  
3.  **[追加]** をクリックします。  
  
     次の図は、送信元スキーマ、送信先スキーマ、およびマッパー グリッドを示します。  
  
     ![MapToReqDenied マップ](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")  
  
4.  **送信元スキーマ**ウィンドウで、をクリックして**ソース スキーマを開く**します。  
  
5.  **BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**、 をクリックして**eaischemas.request**順にクリックします**Ok**します。  
  
6.  **送信元スキーマ**ウィンドウで、右クリックして**\<スキーマ\>**、順にクリックします**ツリー ノードの展開**します。  
  
7.  **送信先スキーマ**ウィンドウで、をクリックして**送信先スキーマを開く**します。  
  
8.  **BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**、 をクリックして**eaischemas.requestdecline**、し、クリックして**OK**します。  
  
9. **送信先スキーマ**ウィンドウで、右クリックして**\<スキーマ\>**、順にクリックします**ツリー ノードの展開**します。  
  
10. **送信元スキーマ**ウィンドウで、ドラッグ、 **ReqID**フィールドを**ReqID**で、**送信先スキーマ**ウィンドウ。 2 つの要素を接続する線が表示されます。  
  
11. **送信元スキーマ**ウィンドウで、ドラッグ、 **GrandTotal**フィールドを**GrandTotal**フィールドに、**送信先スキーマ**ペイン、データをマップするには他の 1 つのスキーマです。  
  
12. **ファイル** メニューのをクリックして**すべて保存**作業を保存できます。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、要求メッセージを RequestDecline メッセージに変換するマップを作成します。  
  
## <a name="next-steps"></a>次の手順  
 EAISchemas プロジェクトをビルドするとします。  
  
## <a name="see-also"></a>参照  
 [ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)   
 [手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)   
 [ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)   
 [手順 4:マップを作成します。](../core/step-4-create-the-map.md)   
 [手順 5:EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)