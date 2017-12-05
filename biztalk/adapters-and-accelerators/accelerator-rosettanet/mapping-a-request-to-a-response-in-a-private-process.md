---
title: "プライベート プロセスで応答する要求をマッピング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966ad6ad752c36be36b4013743eaba3af5434d0a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a>プライベート プロセスで応答する要求のマッピング
このトピックにプライベート応答側のプロセスで受信した要求メッセージをマップする方法について説明: から、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を応答メッセージを送信できる、応答側パブリック プロセス、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]応答側パブリック プロセス。  
  
 応答側が要求メッセージを受信すると、その要求メッセージは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によってパブリック プロセス オーケストレーションからプライベート プロセス オーケストレーション、基幹業務 (LOB) プログラムへとルーティングされます。 応答側では、RosettaNet 応答メッセージを生成し、開始側に返すために、LOB プログラムからの応答サービス コンテンツを必要とします。 応答メッセージ内の多くの要素では、要求メッセージの値が使用されます。 その結果、応答側プライベート プロセス オーケストレーションにマップを統合することにより、LOB プログラムで必要な形式の応答サービス コンテンツ メッセージを生成できます。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、応答側プライベート プロセスにマップを追加する際に使用できる次のサンプルが含まれています。  
  
-   [3A2 要求から 3A2 応答へのマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [3A4 要求から 3A4 応答へのマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [ダブルアクション PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a>マップを作成するには、次の操作を行います。  
  
1.  開始**Microsoft Visual Studio 2012**です。  
  
2.  **ファイル** メニューのをポイント**開く**、順にクリック**プロジェクト**です。  
  
3.  マップを追加するプライベート プロセス オーケストレーションを含んでいる BizTalk プロジェクトを格納するフォルダーを選択します。  
  
4.  ソリューション エクスプローラーで、プロジェクトを右クリックして **[追加]** をポイントし、**[新しい項目]** をクリックします。  
  
5.  新しい項目の追加 ウィンドウで、**カテゴリ** ウィンドウで、をクリックして**マップ ファイル**です。 テンプレート ウィンドウで **マップ**です。 **名前**ボックスで、マップの名前を入力し、をクリックして**開く**です。  
  
6.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
7.  BizTalk 型の選択 ウィンドウで、**スキーマ**、クリックしてから、マップする要求メッセージの PIP スキーマを選択して**OK**です。  
  
8.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
9. BizTalk 型の選択 ウィンドウで、**参照**、展開**Microsoft.Solutions.BTARN.Schemas.RNPIPs**、展開**スキーマ**、PIP スキーマを選択しますをクリックし、マップ先の応答メッセージ**OK**です。  
  
10. 右クリックし、 \<*スキーマ*\>をクリックし、送信元スキーマのノード**ツリー ノードの展開**です。  
  
11. 送信先スキーマについても、手順 10. を繰り返します。  
  
12. 送信元スキーマ ペインで、送信先スキーマのフィールドにマップするフィールドをクリックしたままにし、 送信先スキーマ ペインで対応するノードにドラッグします。  
  
13. 両スキーマ間でマップする必要のあるすべてのフィールドについて、手順 12. を繰り返します。  
  
14. マップの検証とテストを行います。 詳細については、BizTalk Server ヘルプの「マップのコンパイルとテスト」トピックを参照してください。  
  
### <a name="to-add-the-map-to-the-orchestration"></a>オーケストレーションにマップを追加するには  
  
1.  ソリューション エクスプローラで、プライベート プロセス オーケストレーションをダブルクリックします。  
  
    > [!NOTE]
    >  オーケストレーションに、スキーマを含んでいるアセンブリへの参照があることを確認します。  
  
2.  ツールボックスで、をクリックして、**変換**図形し、する要求メッセージを応答メッセージに変換する必要があるオーケストレーション内の位置にドラッグします。  
  
    > [!NOTE]
    >  配置の例については、**変換**図形の PIP3A4PrivateResponder.odx オーケストレーションを参照してください。 ある\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\3a4\pr です。 このサンプルでは、**変換**図形のすぐ下、 **IsActivityDoubleAction**図形です。 詳細については、次を参照してください。 [3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)です。  
  
    > [!NOTE]
    >  複数の Pip の複数のマップを組み込む方法の例は、次を参照してください。 [Double Action PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)です。  
  
3.  オーケストレーション デザイン画面でクリックして**ConstructMessage1**です。 プロパティ ウィンドウで、図形の名前、および作成するメッセージの名前を入力します。  
  
4.  オーケストレーション デザイン画面でクリックして**変換**です。 プロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) の横に**マップ名**です。  
  
5.  変換の構成 ウィンドウで、**既存のマップ**、し、**完全修飾マップ名**、先ほど作成したマップをクリックします。  
  
6.  **変換**をクリックして**ソース**です。 変数の下の空のボックスをクリックし、ドロップダウン リストから要求メッセージの名前を選択します。  
  
7.  **変換**をクリックして**先**です。 変数の下の空のボックスをクリックし、ドロップダウン リストから応答メッセージの名前を選択します。  
  
8.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)