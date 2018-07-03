---
title: '手順 1: スキーマ DLL2 の参照 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1db92227-6164-42b9-b60c-12dd2cae46e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58156c64ae9954115ff214518879c4cd17e7417
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984331"
---
# <a name="step-1-reference-the-schema-dll"></a>手順 1: スキーマ DLL を参照します。
BizTalk では、メッセージを変更できません。 したがって、プロパティ値を変更するには、新しいメッセージを作成して変更する必要があります。 作成し、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。  
  
 最初に、ただし、する必要があります、スキーマ DLL を参照、j. d. へのアクセス Edwards コンテキスト プロパティです。  
  
### <a name="to-reference-the-schema-dll"></a>スキーマ DLL を参照するには  
  
1. プロジェクト用の作業フォルダ (たとえば c:\class\JDE\BeginDoc) と、テスト XML を格納するフォルダ (たとえば c:\class\JDE\input) を作成します。  
  
2. J. d. に要求を送信するには、静的な送信請求-応答送信ポートの作成します。 Edwards OneWorld します。  
  
    ![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")  
  
3. ソリューション エディターで、プロジェクトを右クリックします。  
  
   1. 選択**追加**を選択します**生成した項目の追加**、 をクリックし、**アダプターの追加**します。  
  
   2. J. d. の Microsoft BizTalk アダプターを選択します。 Edwards OneWorld および作成したポート。  
  
   3. **アダプターの追加ウィザード**、 **CSALES\B4200310**します。  
  
   4. をクリックして**完了**メッセージの形式を含むスキーマを生成します。  
  
      ![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")  
  
4. Visual Studio で、ソリューション エクスプローラを開きます。  
  
5. 右クリックして**参照**、し、**参照の追加**します。  
  
6. **参照の追加**画面で、、**参照**ボタンをクリックします。  
  
    ![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")  
  
7. **コンポーネントの選択**画面には、%SystemDrive%\Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin に移動します。  
  
8. 選択**Microsoft.Adapters.JDEProperties.dll**、 をクリックし、**オープン**します。  
  
9. **参照の追加**に画面で、DLL が表示されます、**選択されたコンポーネント**セクション。  
  
     ![](../core/media/jde-properties-selection.gif "JDE_properties_selection")  
  
10. **[OK]** をクリックします。  
  
11. オーケストレーションをダブルクリックしてオーケストレーション デザイナにアクセスします。  
  
     \- または -  
  
     選択**ビュー**を選択します**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
     [オーケストレーションの種類] が表示されます。  
  
## <a name="see-also"></a>参照  
 [手順 2: オーケストレーションを作成します。](../core/step-2-create-the-orchestration1.md)   
 [手順 3: が完了し、プロジェクトを実行](../core/step-3-complete-and-run-the-project2.md)   
 [手順 4: サンプル XML BeginDoc の作成](../core/step-4-create-a-sample-xml-begindoc1.md)