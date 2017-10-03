---
title: "手順 1: 参照スキーマ DLL2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db92227-6164-42b9-b60c-12dd2cae46e2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b009e2c79c0ea68030561c51e3a90ceef24eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-reference-the-schema-dll"></a>手順 1: スキーマ DLL を参照します。
BizTalk では、メッセージを変更できません。 したがって、プロパティ値を変更するには、新しいメッセージを作成して変更する必要があります。 作成して、受信および送信図形の間でメッセージの割り当て図形を挿入することで、新しいメッセージを変更します。  
  
 最初に、ただし、する必要があります、スキーマ DLL を参照、j. d. へのアクセス Edwards コンテキスト プロパティです。  
  
### <a name="to-reference-the-schema-dll"></a>スキーマ DLL を参照するには  
  
1.  プロジェクト用の作業フォルダ (たとえば c:\class\JDE\BeginDoc) と、テスト XML を格納するフォルダ (たとえば c:\class\JDE\input) を作成します。  
  
2.  J. d. に要求を送信する静的な送信請求-応答送信ポートを作成します。 Edwards OneWorld です。  
  
     ![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")  
  
3.  ソリューション エディターで、プロジェクトを右クリックします。  
  
    1.  選択**追加****生成した項目の追加**、順にクリック**アダプターの追加**です。  
  
    2.  Microsoft BizTalk Adapter の j. d. を選択します。 Edwards OneWorld および作成したポートです。  
  
    3.  **アダプターの追加ウィザード** **csales \b4200310**です。  
  
    4.  をクリックして**完了**メッセージの形式を含むスキーマを生成します。  
  
     ![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")  
  
4.  Visual Studio で、ソリューション エクスプローラを開きます。  
  
5.  右クリック**参照**、し、**参照の追加**です。  
  
6.  **参照の追加**画面で、をクリックして、**参照**ボタンをクリックします。  
  
     ![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")  
  
7.  **コンポーネントの選択**画面で、%SystemDrive%\Program files \common files \microsoft BizTalk Adapters for Enterprise applications \bin 移動します。  
  
8.  選択**Microsoft.Adapters.JDEProperties.dll**、クリックして**開く**です。  
  
9. **参照の追加**に 画面で、DLL が表示されます、**選択されたコンポーネント**セクションです。  
  
     ![](../core/media/jde-properties-selection.gif "JDE_properties_selection")  
  
10. **[OK]**をクリックします。  
  
11. オーケストレーションをダブルクリックしてオーケストレーション デザイナにアクセスします。  
  
     \- または -  
  
     選択**ビュー****その他のウィンドウ**、順にクリック**オーケストレーションの種類**。  
  
     [オーケストレーションの種類] が表示されます。  
  
## <a name="see-also"></a>参照  
 [手順 2: オーケストレーションを作成します。](../core/step-2-create-the-orchestration1.md)   
 [手順 3: が完了し、プロジェクトを実行](../core/step-3-complete-and-run-the-project2.md)   
 [手順 4: サンプル XML BeginDoc を作成します。](../core/step-4-create-a-sample-xml-begindoc1.md)