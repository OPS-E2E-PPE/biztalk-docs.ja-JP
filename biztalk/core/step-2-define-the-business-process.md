---
title: 手順 2:ビジネス プロセスの定義 |Microsoft Docs
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
ms.openlocfilehash: 0e68039f069da758961f125854fd483f0e5b4042
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392719"
---
# <a name="step-2-define-the-business-process"></a>手順 2:ビジネス プロセスを定義します。
![手順 4 2](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 8 分  
  
 **目標:** この手順では、オーケストレーション デザイナーを使用して、ビジネス プロセスを定義します。  
  
 **目的:** オーケストレーションのワークフローを表し在庫補充要求を承認するため、会社のビジネス プロセスを自動化します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 1。EAIOrchestration プロジェクトをソリューションに追加](../core/step-1-add-eaiorchestration-project-to-the-solution.md)します。  
  
## <a name="procedures"></a>手順  
 オーケストレーションを開発するための最初の手順では、ビジネス プロセスを表すアクション図形を使用します。  
  
#### <a name="to-create-the-eai-business-process-workflow"></a>EAI ビジネス プロセスのワークフローを作成するには  
  
1. Visual studio で、ソリューション エクスプ ローラーでダブルクリック**EAIProcess.odx**オーケストレーションを開きます。  
  
2. オーケストレーション デザイナで、オーケストレーション ツールボックスからドラッグして、**受信**図形し、の間にドロップ、**開始**(緑色の円) と**エンド**図形 (赤色の八角形)。  
  
   > [!NOTE]
   >  ツールボックスが開かれていない場合、**ビュー**  メニューのをクリックして**ツールボックス**します。 画面に固定しを画鋲のアイコンをクリックします。  
  
3. ツールボックスからドラッグして、**判断**図形、受信図形の下にします。  
  
4. ツールボックスからドラッグして、**変換**決定図形の左の分岐に図形。 変換図形がメッセージの構築図形内で入れ子になった。  
  
5. ツールボックスからドラッグして、**送信**図形、変換図形の下にします。  
  
6. ツールボックスからドラッグして、**送信**決定図形の右の分岐に図形。  オーケストレーションは、アクション図形を追加した後、次のようになります。  
  
    ![EAI プロセス](../core/media/eaiprocess.gif "EAIProcess")  
  
   次の手順では、メッセージ変数を定義します。  いくつかのアクション図形を指定する必要があるメッセージ プロパティがあります。  
  
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
    |**マップ名**|クリックして **.**. 変換の構成では、次の操作を行います。<br /><br /> 構成情報を入力します。<br /><br /> -**既存のマップ**します。<br /><br /> 完全修飾マップ名:<br /><br /> - **\<参照されたアセンブリから選択\>** します。  左側のウィンドウから次のように選択します。 **EAISchemas**します。  右側のウィンドウから eaischemas.maptoreqdecline をクリックを選択します。  **[OK]** をクリックします。<br /><br /> ソース<br /><br /> -RequestMessage<br /><br /> [Destination]<br /><br /> -RequestDeclineMessage|  
  
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
 この手順では、オーケストレーション デザイナーを使用して、ビジネス プロセスを定義します。  
  
## <a name="next-steps"></a>次の手順  
 では、オーケストレーションに論理ポートを追加する[手順 3。ポートをオーケストレーションに追加](../core/step-3-add-ports-to-the-orchestration.md)します。  
  
## <a name="see-also"></a>参照  
 [ステップ 1: EAIOrchestration プロジェクトをソリューションに追加します。](../core/step-1-add-eaiorchestration-project-to-the-solution.md)   
 [ステップ 3:ポートをオーケストレーションに追加します。](../core/step-3-add-ports-to-the-orchestration.md)   
 [手順 4:EAIOrchestration プロジェクトをビルドします。](../core/step-4-build-the-eaiorchestration-project.md)