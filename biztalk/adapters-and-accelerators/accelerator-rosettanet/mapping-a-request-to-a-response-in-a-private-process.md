---
title: プライベート プロセスで応答する要求のマッピング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- private processes, mapping requests
- private processes, customizing
- orchestrations, adding maps
- maps, adding to orchestrations
- maps, creating
- customizing private processes
- requests, mapping
- requests, private processes
ms.assetid: 5452c0a2-3a9b-43e7-bfa7-713eef0eab3b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0ec4be1703c81061cf38310a467932a917bca3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283225"
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a>プライベート プロセスで応答する要求のマッピング
このトピックでは、応答側プライベート プロセスが受信した要求メッセージにマップする方法を説明します: Microsoft から[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を応答メッセージを送信できる、パブリック応答側プロセス、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]応答側パブリック プロセス。  
  
 応答側が要求メッセージを受信すると、その要求メッセージは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によってパブリック プロセス オーケストレーションからプライベート プロセス オーケストレーション、基幹業務 (LOB) プログラムへとルーティングされます。 応答側では、RosettaNet 応答メッセージを生成し、開始側に返すために、LOB プログラムからの応答サービス コンテンツを必要とします。 応答メッセージ内の多くの要素では、要求メッセージの値が使用されます。 その結果、応答側プライベート プロセス オーケストレーションにマップを統合することにより、LOB プログラムで必要な形式の応答サービス コンテンツ メッセージを生成できます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、応答側プライベート プロセスにマップを追加する際に使用できる次のサンプルが含まれています。  
  
-   [3A2 要求から 3A2 応答へのマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [3A4 要求から 3A4 応答へのマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [ダブルアクション PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a>マップを作成するには、次の操作を行います。  
  
1.  開始**Microsoft Visual Studio 2012**します。  
  
2.  **ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。  
  
3.  マップを追加するプライベート プロセス オーケストレーションを含んでいる BizTalk プロジェクトを格納するフォルダーを選択します。  
  
4.  ソリューション エクスプローラーで、プロジェクトを右クリックして **[追加]** をポイントし、**[新しい項目]** をクリックします。  
  
5.  [新しい項目の追加] ウィンドウで、**カテゴリ**ウィンドウで、をクリックして**マップ ファイル**。 [テンプレート] ペインで次のようにクリックします。**マップ**します。 **名前**ボックスで、マップの名前を入力し、クリックして**オープン**します。  
  
6.  送信元スキーマ ペインで次のようにクリックします。**ソース スキーマを開く**します。  
  
7.  BizTalk 型の選択 ウィンドウで、**スキーマ**をクリックしてから、マップする要求メッセージの PIP スキーマを選択します。 **OK**します。  
  
8.  送信先スキーマ ペインで次のようにクリックします。**送信先スキーマを開く**します。  
  
9. BizTalk 型の選択 ウィンドウで、**参照**、展開**microsoft.solutions.btarn.schemas.rnpips**、展開**スキーマ**、PIP スキーマを選択します応答メッセージをクリックし、マップする**OK**します。  
  
10. 右クリックし、 \<*スキーマ*\>クリック、送信元スキーマのノード**ツリー ノードの展開**します。  
  
11. 送信先スキーマについても、手順 10. を繰り返します。  
  
12. 送信元スキーマ ペインで、送信先スキーマのフィールドにマップするフィールドをクリックしたままにし、 送信先スキーマ ペインで対応するノードにドラッグします。  
  
13. 両スキーマ間でマップする必要のあるすべてのフィールドについて、手順 12. を繰り返します。  
  
14. マップの検証とテストを行います。 詳細については、BizTalk Server ヘルプで「マップのコンパイルとテスト」のトピックを参照してください。  
  
### <a name="to-add-the-map-to-the-orchestration"></a>オーケストレーションにマップを追加するには  
  
1.  ソリューション エクスプローラで、プライベート プロセス オーケストレーションをダブルクリックします。  
  
    > [!NOTE]
    >  オーケストレーションに、スキーマを含んでいるアセンブリへの参照があることを確認します。  
  
2.  ツールボックスで、をクリックして、**変換**図形、および位置は、要求メッセージを応答メッセージに変換する必要があるオーケストレーション内の位置にドラッグします。  
  
    > [!NOTE]
    >  配置の例については、**変換**図形、PIP3A4PrivateResponder.odx オーケストレーションを参照してください。 ある\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\3a4\pr です。 このサンプルでは、**変換**図形のすぐ下、 **IsActivityDoubleAction**図形。 詳細については、次を参照してください。 [3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)します。  
  
    > [!NOTE]
    >  複数の Pip の複数のマップを組み込む方法の例は、次を参照してください。 [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)します。  
  
3.  オーケストレーション デザイン画面でクリックして**ConstructMessage1**します。 プロパティ ウィンドウで、図形の名前、および作成するメッセージの名前を入力します。  
  
4.  オーケストレーション デザイン画面でクリックして**変換**します。 [プロパティ] ウィンドウで、省略記号ボタンをクリックします (**...**) 横に**マップ名**します。  
  
5.  変換の構成 ウィンドウで、次のようにクリックします。**既存のマップ**、および**完全修飾マップ名**、先ほど作成したマップをクリックします。  
  
6.  [**変換**、] をクリックして**ソース**します。 変数の下の空のボックスをクリックし、ドロップダウン リストから要求メッセージの名前を選択します。  
  
7.  [**変換**、] をクリックして**先**します。 変数の下の空のボックスをクリックし、ドロップダウン リストから応答メッセージの名前を選択します。  
  
8.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)