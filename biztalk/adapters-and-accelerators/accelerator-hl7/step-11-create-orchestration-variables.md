---
title: '手順 11: オーケストレーション変数の作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
- message enrichment tutorial, orchestrations
ms.assetid: 3d1f792d-fe74-4373-86fa-3debda55e732
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfe49f533989e339e6eb4318460a444ed0d8b741
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991163"
---
# <a name="step-11-create-orchestration-variables"></a>手順 11: オーケストレーション変数を作成します。
この手順では、オーケストレーションによって送受信されたメッセージ インスタンスのオーケストレーション変数を作成します。  
  
 BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) シリアライザーでは、次の要素の名前。 マルチパート メッセージを作成するには、その他の部分の名前と、シリアライザーは、メッセージを拒否します。 メッセージ要素の名前は次のとおりです。  
  
- MSHSegment  
  
- BodySegments  
  
- Z セグメント  
  
  Z セグメントの部分に関する重要な情報を次に示します。  
  
- すべてのメッセージは、Z セグメントが存在するかどうかに関係なく、上記のように 3 つの部分を含んでいます。  
  
- Z セグメントの一部を使用して、末尾や (これも宣言ではないことを意味) スキーマで定義されていませんが、メッセージ インスタンスからデータを格納します。  
  
- 宣言されていないデータがない場合は、Z セグメントの一部が空白です。 BizTalk マッパー; 内の中間 XML を表示するときに、Z セグメントの部分は表示されません。ただし、BizTalk 状態と動作状況の追跡 (HAT) ツールで、3 つの部分を各メッセージが表示されます。  
  
### <a name="to-create-orchestration-variables"></a>オーケストレーション変数を作成するには  
  
1. をクリックして、**オーケストレーション** タブの横に、**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーの下にあるタブ。  
  
2. **オーケストレーション**ウィンドウで、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
3. 変更、**識別子**プロパティ、**プロパティ**ペイン**DoorbellInputMessage**、し、キーを押します **」と入力**します。  
  
4. **プロパティ**ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、 をクリックし、 **BTAHL7_Project.Doorbell**します。  
  
5. 手順 2. および 3. という名前の別のメッセージの作成を**DoorbellOutputMessage**します。  
  
6. **プロパティ**ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、 をクリックし、 **BTAHL7Schemas.ADT_A04_22_GLO_DEF**.  
  
7. **オーケストレーション**ウィンドウで、展開、**型**ノード。 右クリックして**マルチパート メッセージの種類**、 をクリックし、**新しいマルチパート メッセージの種類**します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] という名前の新しいメッセージ型を作成します。 **MultipartType_1**という名前の新しいメッセージと共に**MessagePart_1**します。  
  
8. をクリックして**MultipartType_1**、し、**プロパティ**ウィンドウで、をクリックして**識別子**新しい名前を入力**DoorbellFinalMessageType**、キーを押しますと**Enter**します。  
  
   > [!NOTE]
   >  手順 9 ~ 15 では、マルチパート メッセージの部分を作成します。 マルチパート メッセージの部分を作成する順序が重要です。 常に、ヘッダー、本文し Z セグメントを作成します。  
  
   > [!NOTE]
   >  作成すると、メッセージ部分をという名前が、名前を変更しないことです。 必要に応じて、古いボディ部を削除し、新しい名前で新しいボディ部を作成します。  
  
9. **型**ウィンドウで、**マルチパート メッセージの種類**、展開**DoorbellFinalMessageType**、順にクリックします**MessagePart_1**します。 **プロパティ**ウィンドウで、入力**MSHSegment**の**識別子**、およびキーを押します **」と入力**します。 ドロップダウン リストで**型**、展開 **.NET クラス**、 をクリックし、 \<**参照されたアセンブリから選択\>**。  
  
10. **成果物の種類の選択** ダイアログ ボックスで、左側のウィンドウでクリックして**System.Xml**します。 右側のウィンドウで次のようにクリックします。 **XmlDocument**、 をクリックし、 **OK**します。  
  
11. オーケストレーションの種類 ウィンドウで、右クリック**DoorbellFinalMessageType**、 をクリックし、**メッセージ部分を新しい**MessagePart_1 を作成します。  
  
12. **プロパティ**ウィンドウで、入力**BodySegments**の**識別子**、およびキーを押します **」と入力**します。 ドロップダウン リストで**型**、展開**スキーマ**、し、 **BTAHL7Schemas.ADT_A04_22_GLO_DEF**ドロップダウン リストから。  
  
13. 設定、**メッセージのボディ部**プロパティを**True**します。  
  
14. **オーケストレーション ビュー**ウィンドウで、右クリック**DoorbellFinalMessageType**、順にクリックします**メッセージ部分を新しい**。  
  
15. **プロパティ**ウィンドウで、入力**ZSegments**の**識別子**、およびキーを押します **」と入力**します。 をクリックして**型**、展開 **.NET クラス**、 をクリックし、 **System.String**ドロップダウン リストから。  
  
    > [!NOTE]
    >  使用する**System.String**の Z セグメントのメッセージ部分では、Z セグメントには、スキーマに準拠する必要のない文字列データが含まれています。  
  
16. **オーケストレーション**ウィンドウで、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
17. **プロパティ**ウィンドウで、入力**DoorbellFinalMessage**の**識別子**、およびキーを押します **」と入力**します。 ドロップダウン リストで**メッセージの種類**、展開**マルチパート メッセージの種類**、 をクリックし、 **BTAHL7_Project.DoorbellFinalMessageType**します。  
  
18. **オーケストレーション**ウィンドウで、右クリック**変数**、順にクリックします**新しい変数**します。  
  
19. **プロパティ**ウィンドウで、入力**HeaderInfo**の**識別子**、キーを押します**Enter**。 ドロップダウン リストで**型**、ダブルクリックして\< **.NET クラス\>** します。  
  
20. **成果物の種類の選択**ウィンドウで、左側のウィンドウでクリックして**System.Xml**します。 右側のウィンドウで次のようにクリックします。 **XmlDocument**、 をクリックし、 **OK**します。  
  
21. **ファイル** メニューのをクリックして**すべて保存**します。  
  
    続行する[手順 12: オーケストレーション図形の構成](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)します。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)