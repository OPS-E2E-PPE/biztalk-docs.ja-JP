---
title: 手順 1:スキーマ DLL1 の参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47e4b773-e484-4931-9ab2-b8dd0080ea1c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41fa9a1e50fda5e31cb6a6c49f4b6e758671d103
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392954"
---
# <a name="step-1-reference-the-schema-dll"></a>手順 1:スキーマ DLL を参照します。
BizTalk メッセージは変更できません。 そのため、プロパティ値を変更するには、作成し、新しいメッセージを変更する必要があります。 作成し、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。  
  
 最初に、ただし、する必要があります、スキーマ DLL を参照、j. d. へのアクセス Edwards EnterpriseOne コンテキスト プロパティです。  
  
### <a name="to-reference-the-schema-dll"></a>スキーマ DLL を参照するには  
  
1. たとえば、c:\class\JDE\BeginDoc プロジェクトとテストは、XML c:\class\JDE\input などを格納するフォルダーを作業フォルダーを作成します。  
  
2. J. d. に要求を送信するには、静的な送信請求-応答送信ポートの作成します。 Edwards EnterpriseOne します。  
  
    ![JDOneWorld トランスポート プロパティ](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")  
  
3. ソリューション エディターでは、プロジェクトを右クリックします。  
  
   1. 選択**追加**を選択します**生成した項目の追加**、 をクリックし、**アダプターの追加**します。  
  
   2. J. d. の Microsoft BizTalk アダプターを選択します。 Edwards EnterpriseOne および作成したポート。  
  
   3. **アダプターの追加ウィザード**、 **CSALES\B4200310**します。  
  
   4. をクリックして**完了**メッセージの形式を含むスキーマを生成します。  
  
      ![アダプターの追加ウィザード](../core/media/add-adapter-wizard.gif "add_adapter_wizard")  
  
4. Visual Studio で、ソリューション エクスプ ローラーを開きます。  
  
5. 右クリックして**参照**、し、**参照の追加**します。  
  
6. **参照の追加**画面で、、**参照**ボタンをクリックします。  
  
7. **コンポーネントの選択**画面には、%SystemDrive%\Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin に移動します。  
  
8. 選択**Microsoft.Adapters.JDEProperties.dll**、 をクリックし、**オープン**します。  
  
9. **参照の追加**に画面で、DLL が表示されます、**選択されたコンポーネント**セクション。  
  
     ![プロパティ選択画面](../core/media/properties-selection.gif "properties_selection")  
  
10. **[OK]** をクリックします。  
  
11. オーケストレーション デザイナーにアクセスするオーケストレーションをダブルクリックします。  
  
     \- または -  
  
     選択**ビュー**を選択します**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
     オーケストレーション ビューが表示されます。  
  
## <a name="see-also"></a>参照  
 [手順 2:オーケストレーションを作成します。](../core/step-2-create-the-orchestration2.md)   
 [タスク 4:メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape1.md)   
 [タスク 5:変換図形を構成します。](../core/task-5-configure-the-transform-shape2.md)   
 [ステップ 3:完了して、プロジェクトを実行](../core/step-3-complete-and-run-the-project1.md)   
 [手順 4:サンプル XML BeginDoc を作成します。](../core/step-4-create-a-sample-xml-begindoc2.md)