---
title: '手順 4: マップの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 9fcbce54a488cb687ad0fb2c7a1931243c8cd882
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973984"
---
# <a name="step-4-create-the-map"></a>ステップ 4: マップの作成
![手順 5 の 4](../core/media/step-4of5.gif "Step_4of5")  
  
 **所要時間:** 6 分  
  
 **目標:** この手順では、要求メッセージを RequestDecline メッセージに変換するマップを作成します。  
  
 **目的:** マップ、倉庫在庫システムに返される要求拒否メッセージで、要求 ID 番号と総計が含まれていることを確認します。 ここでは BizTalk マッパーを使用して、送信メッセージ用に定義されているフィールドに受信メッセージのフィールドを関連付けます。 この操作は、2 種類のメッセージのスキーマ構造が異なるため、必要です。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 2: 在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)と[手順 3: 要求拒否スキーマを作成する](../core/step-3-create-the-request-decline-schema.md)です。  
  
## <a name="procedures"></a>手順  
 マップは、Request スキーマまたは RequestDecline スキーマのいずれであるかによって異なります。  これらのスキーマをマップで使用するには、スキーマを使用してプロジェクトをコンパイルする必要があります。  
  
#### <a name="to-compile-the-eaischemas-project"></a>EAISchemas プロジェクトをコンパイルするには  
  
-   ソリューション エクスプ ローラーで右クリック**EAISchemas**、クリックして**ビルド**です。  
  
#### <a name="to-create-the-map"></a>マップを作成するには、次の操作を行います。  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  **新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストールされたテンプレート**|をクリックして**マップ ファイル**、クリックして**マップ**です。|  
    |**名前**|型**MapToReqDecline.btm**です。|  
  
3.  **[追加]** をクリックします。  
  
     送信元スキーマ、送信先スキーマ、およびマッパー グリッドを次に示します。  
  
     ![MapToReqDenied マップ](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")  
  
4.  **送信元スキーマ** ウィンドウで、をクリックして**ソース スキーマを開く**です。  
  
5.  **BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**をクリックして**eaischemas.request**をクリックして**Ok**です。  
  
6.  **送信元スキーマ** ウィンドウを右クリックして**\<スキーマ\>**、クリックして**ツリー ノードの展開**です。  
  
7.  **送信先スキーマ** ウィンドウで、をクリックして**送信先スキーマを開く**です。  
  
8.  **BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**をクリックして**eaischemas.requestdecline**、し、をクリックして**OK**です。  
  
9. **送信先スキーマ** ウィンドウを右クリックして**\<スキーマ\>**、クリックして**ツリー ノードの展開**です。  
  
10. **送信元スキーマ** ウィンドウで、ドラッグ、 **ReqID**フィールドを**ReqID**で、**送信先スキーマ**ウィンドウです。 これら 2 要素を接続する線が表示されます。  
  
11. **送信元スキーマ** ウィンドウで、ドラッグ、 **GrandTotal**フィールドを**GrandTotal**フィールドで、**送信先スキーマ**ペイン、データをマップするには他の 1 つのスキーマです。  
  
12. **ファイル** メニューのをクリックして**すべて保存**作業内容を保存します。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、Request メッセージを RequestDecline メッセージに変換するマップを作成しました。  
  
## <a name="next-steps"></a>次の手順  
 EAISchemas プロジェクトをビルドします。  
  
## <a name="see-also"></a>参照  
 [手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)   
 [手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)   
 [手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)   
 [手順 4: マップを作成します。](../core/step-4-create-the-map.md)   
 [手順 5: EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)