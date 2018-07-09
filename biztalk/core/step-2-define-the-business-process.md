---
title: '手順 2: ビジネス プロセスの定義 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b37bd9f1-5ee2-434d-950a-cf12967b6fc2
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850b8b98764bc782dc62c6ebe792ace2d80ef0a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998107"
---
# <a name="step-2-define-the-business-process"></a>ステップ 2: ビジネス プロセスの定義
![手順 4 2](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 8 分  
  
 **目標:** この手順で、ビジネス プロセスを定義するオーケストレーション デザイナーを使用します。  
  
 **目的:** オーケストレーションのワークフローを表すし、在庫補充要求を承認するため、会社のビジネス プロセスを自動化します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 1: EAIOrchestration プロジェクトをソリューションに追加](../core/step-1-add-eaiorchestration-project-to-the-solution.md)します。  
  
## <a name="procedures"></a>手順  
 オーケストレーションの開発のための最初の手順は、アクション図形を使用してビジネス プロセスを表すことです。  
  
#### <a name="to-create-the-eai-business-process-workflow"></a>EAI ビジネス プロセスのワークフローを作成するには  
  
1. Visual studio で、ソリューション エクスプ ローラーでダブルクリック**EAIProcess.odx**オーケストレーションを開きます。  
  
2. オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**受信**図形し、の間にドロップ、**開始**(緑色の円) と**エンド**図形 (赤色の八角形)。  
  
   > [!NOTE]
   >  ツールボックスが開かれていない場合、**ビュー**  メニューのをクリックして**ツールボックス**します。 ツールボックスを画面上に固定するには、画鋲のアイコンをクリックします。  
  
3. ツールボックスからドラッグして、**判断**図形、受信図形の下にします。  
  
4. ツールボックスからドラッグして、**変換**決定図形の左の分岐に図形。 変換図形は メッセージの構築図形で入れ子になっています。  
  
5. ツールボックスからドラッグして、**送信**図形、変換図形の下にします。  
  
6. ツールボックスからドラッグして、**送信**決定図形の右の分岐に図形。  操作図形を追加すると、オーケストレーションは次のようになります。  
  
    ![EAI プロセス](../core/media/eaiprocess.gif "EAIProcess")  
  
   次の手順では、メッセージ変数を定義します。  操作によっては、メッセージ プロパティを指定する必要があります。  
  
#### <a name="to-define-message-variables"></a>メッセージ変数を定義するには  
  
1.  Visual studio で、をクリックして、**ビュー**  メニューのをクリックして**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
2.  オーケストレーションの種類を右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
3.  [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[Identifier]**|型**RequestMessage**します。|  
    |**メッセージの種類**|をクリックして**スキーマ**、 をクリックし、 **\<参照されたアセンブリから選択しています.\>**. 成果物の種類の選択 ウィンドウで、 **EAISchemas**、 をクリックし、**要求**します。 **[OK]** をクリックします。|  
  
4.  オーケストレーションの種類を右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
5.  [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[Identifier]**|型**RequestDeclineMessage**します。|  
    |**メッセージの種類**|をクリックして**スキーマ**、 をクリックし、 **\<参照されたアセンブリから選択しています.\>**. アイテムの種類 ウィンドウで、 **EAISchemas**、 をクリックし、 **RequestDecline**します。 **[OK]** をクリックします。|  
  
#### <a name="to-configure-the-properties-of-the-shapes"></a>図形のプロパティを構成するには  
  
1.  デザイン画面でクリックして、**受信**図形を選択します。  
  
2.  [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ReceiveRequest**します。|  
    |**メッセージ**|選択**RequestMessage**します。|  
    |**Activate**|ドロップダウン リストから選択**True**します。|  
  
    > [!NOTE]
    >  プロパティ ウィンドウが開いていない場合、**ビュー**  メニューのをクリックして**プロパティ ウィンドウ**します。  
  
3.  デザイン画面でクリックして、**判断**図形。  
  
4.  [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**CheckGrandTotal**します。|  
  
    > [!NOTE]
    >  プロパティ ウィンドウが開いていない場合、**ビュー**  メニューのをクリックして**プロパティ ウィンドウ**します。  
  
5.  デザイン画面でクリックして、 **[rule_1]** 図形。  
  
6.  [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**DeclineRule**します。|  
    |**[式]**|省略記号をクリックします (**.**)、し、入力`RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`します。 **[OK]** をクリックします。|  
  
7.  デザイン画面でクリックして、 **ConstructMessage_1**図形。  
  
8.  [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**ConstructRequestDeclineMessage**します。|  
    |**構築メッセージ**|選択**RequestDeclineMessage**します。|  
  
9. デザイン画面でクリックして、**変換 _ 1**図形。  
  
10. [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**TransformRequestToRequestDeclineMessage**します。|  
    |**マップ名**|クリックして **.**. [変換の構成] で、次の操作を行います。<br /><br /> 構成情報の入力<br /><br /> -**既存のマップ**します。<br /><br /> 完全修飾マップ名:<br /><br /> - **\<参照されたアセンブリから選択\>** します。  左側のウィンドウから次のように選択します。 **EAISchemas**します。  右ペインで、[EAISchemas.MapToReqDecline] をクリックします。  **[OK]** をクリックします。<br /><br /> Source<br /><br /> -RequestMessage<br /><br /> [Destination]<br /><br /> -RequestDeclineMessage|  
  
11. デザイン画面でクリックして、 **Send_1**図形。  
  
12. [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**SendRequestDecline**します。|  
    |**メッセージ**|選択**RequestDeclineMessage**します。|  
  
13. デザイン画面でクリックして、 **[send_2]** 図形。  
  
14. [プロパティ ウィンドウ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**SendRequestToERP**します。|  
    |**メッセージ**|選択**RequestMessage**します。|  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 このステップでは、オーケストレーション デザイナーを使用して、ビジネス プロセスを定義しました。  
  
## <a name="next-steps"></a>次の手順  
 では、オーケストレーションに論理ポートを追加する[手順 3: 追加のポートをオーケストレーションに](../core/step-3-add-ports-to-the-orchestration.md)。  
  
## <a name="see-also"></a>参照  
 [手順 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [手順 3: オーケストレーションのポートを追加します。](../core/step-3-add-ports-to-the-orchestration.md)   
 [手順 4: EAIOrchestration プロジェクトのビルド](../core/step-4-build-the-eaiorchestration-project.md)