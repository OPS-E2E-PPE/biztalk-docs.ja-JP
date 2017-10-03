---
title: "手順 11: オーケストレーション変数を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
- message enrichment tutorial, orchestrations
ms.assetid: 3d1f792d-fe74-4373-86fa-3debda55e732
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c12a437371c5412cfafa4140e74733655962fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-11-create-orchestration-variables"></a>手順 11: オーケストレーション変数を作成します。
このステップでは、オーケストレーションによって送受信されたメッセージ インスタンスのオーケストレーション変数を作成します。  
  
 BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) シリアライザーでは、次の要素の名前。 他の部分名を持つ、マルチパート メッセージを作成する場合、シリアライザーは、メッセージを拒否します。 メッセージ部分名は次のとおりです。  
  
-   MSHSegment  
  
-   BodySegments  
  
-   Z セグメント  
  
 Z セグメント パーツに関する重要な情報を次に示します。  
  
-   すべてのメッセージは、かどうか、Z セグメントは存在するかに関係なく、前述のように、3 つの部分を含んでいます。  
  
-   Z セグメントの一部を使用するには、末尾 (つまりも宣言されていないこと) スキーマで定義されていないメッセージのインスタンスからデータを格納します。  
  
-   宣言されていないデータがない場合は、Z のセグメントの一部が空白です。 BizTalk マッパー; 内の中間 XML を表示するときに Z セグメント部分は表示されません。ただし、BizTalk 状態と動作状況の追跡 (HAT) ツールで、各メッセージに 3 つの部分を表示します。  
  
### <a name="to-create-orchestration-variables"></a>オーケストレーション変数を作成するには  
  
1.  クリックして、**オーケストレーション ビュー**  タブの横に、**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーの下にあるタブ。  
  
2.  **オーケストレーション** ウィンドウを右クリックして**メッセージ**、順にクリック**新しいメッセージ**です。  
  
3.  変更、**識別子**プロパティに、**プロパティ**ペイン**DoorbellInputMessage**、キーを押します**Enter**です。  
  
4.  **プロパティ**ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、クリックして**BTAHL7_Project.Doorbell**です。  
  
5.  手順 2 および 3 という名前の別のメッセージを作成する**DoorbellOutputMessage**です。  
  
6.  **プロパティ**ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、クリックして**BTAHL7Schemas.ADT_A04_22_GLO_DEF**.  
  
7.  **オーケストレーション** ウィンドウで、展開、**型**ノード。 右クリック**マルチパート メッセージの種類**、クリックして**新しいマルチパート メッセージの種類**です。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]という名前の新しいメッセージ型を作成**MultipartType_1**という名前の新しいメッセージと共に**MessagePart_1**です。  
  
8.  をクリックして**MultipartType_1**、し、、**プロパティ**ウィンドウで、をクリックして**識別子**新しい名前を入力して**DoorbellFinalMessageType**、キーを押します**Enter**です。  
  
    > [!NOTE]
    >  手順 9 ~ 15 では、マルチパート メッセージの部分を作成します。 マルチパート メッセージの部分を作成する順序が重要です。 常に、ヘッダー、本文し Z セグメントを作成します。  
  
    > [!NOTE]
    >  1 回作成し、メッセージ部分をという名前を変更しないこと。 必要に応じて、古いボディ部を削除し、新しい名前で新しいボディ部を作成します。  
  
9. **型**ウィンドウで、**マルチパート メッセージの種類**、展開**DoorbellFinalMessageType**、順にクリック**MessagePart_1**です。 **プロパティ** ウィンドウで、入力**MSHSegment**の**識別子**、キーを押します**Enter**です。 ドロップダウン リストで**型**、展開**.NET クラス**、クリックして\<**参照されたアセンブリから選択 >**です。  
  
10. **成果物の種類の選択**ダイアログ ボックスで、左側のウィンドウでをクリックして**System.Xml**です。 右側のウィンドウでをクリックして**XmlDocument**、クリックして**OK**です。  
  
11. オーケストレーションの種類 ウィンドウで、右クリック**DoorbellFinalMessageType**、クリックして**新しいメッセージ部分**MessagePart_1 を作成します。  
  
12. **プロパティ**ウィンドウで、入力**BodySegments**の**識別子**、キーを押します**Enter**です。 ドロップダウン リストで**型**、展開**スキーマ**、し、 **BTAHL7Schemas.ADT_A04_22_GLO_DEF**ドロップダウン リストからです。  
  
13. 設定、**メッセージのボディ部**プロパティを**True**です。  
  
14. **オーケストレーション**ウィンドウを右クリックして**DoorbellFinalMessageType**、順にクリック**新しいメッセージ部分**です。  
  
15. **プロパティ** ウィンドウで、入力**ZSegments**の**識別子**、キーを押します**Enter**です。 をクリックして**型**、展開**.NET クラス**、順にクリック**System.String**ドロップダウン リストからです。  
  
    > [!NOTE]
    >  使用する**System.String** Z が Z セグメントには、スキーマに準拠する必要のない文字列データが含まれているために、メッセージ部分をセグメントのです。  
  
16. **オーケストレーション**ウィンドウを右クリックして**メッセージ**、順にクリック**新しいメッセージ**です。  
  
17. **プロパティ**ウィンドウで、入力**DoorbellFinalMessage**の**識別子**、キーを押します**Enter**です。 ドロップダウン リストで**メッセージの種類**、展開**マルチパート メッセージの種類**、クリックして**BTAHL7_Project.DoorbellFinalMessageType**です。  
  
18. **オーケストレーション**ウィンドウを右クリックして**変数**、順にクリック**新しい変数**です。  
  
19. **プロパティ** ウィンドウで、入力**HeaderInfo**の**識別子**、キーを押します**Enter**です。 ドロップダウン リストで**型**をダブルクリックして\< **.NET クラス >**です。  
  
20. **成果物の種類の選択**ウィンドウの左側のウィンドウでをクリックして**System.Xml**です。 右側のウィンドウでをクリックして**XmlDocument**、クリックして**OK**です。  
  
21. **ファイル** メニューのをクリックして**すべて保存**です。  
  
 進みます[手順 12: オーケストレーション図形を構成する](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)