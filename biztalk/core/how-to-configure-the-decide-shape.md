---
title: 判断図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Decide shape [Orchestration Designer]
- Decide shape [Orchestration Designer], configuring
- Decide shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Decide shapes
ms.assetid: 70910861-3834-49e7-ab1e-d62730ea2a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cadca52dade623190b347c0daa3cbd5581c58b2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341027"
---
# <a name="how-to-configure-the-decide-shape"></a>判断図形を構成する方法
![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")  
判断図形  
  
 各分岐を**判断**図形、以外、**他**分岐で、ルールと、対応します。 BizTalk 式エディターを使用して、その分岐を実行するために評価されるルールのブール式を作成することができます。 **他**ブランチ直前の分岐のブール式の否定を意味する、関連付けられている式がありません。  
  
 ルールの下または**他**句では、分岐を**判断**図形がオーケストレーションの他の部分と同様、追加の図形を含めることができます。  
  
### <a name="to-configure-a-decide-shape"></a>判断図形を構成するには  
  
1.  BizTalk 式エディターが表示されない場合、ルールを右クリックし、クリックして**ブール式の編集**、プロパティ ウィンドウで次のようにクリックしますまたは、**省略記号**(**...。**) ボタンを**式**プロパティ。  
  
2.  BizTalk 式エディターでは、以外の各分岐のブール式を作成、 **Else**分岐します。 例を次に示します。  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a>判断図形に分岐を追加するには  
  
1.  右クリックし、**判断**図形をクリックして**新しいルール分岐**します。  
  
     - または -  
  
2.  既存の 2 つの分岐の間には、新しい図形をドラッグします。  
  
    > [!NOTE]
    >  分岐を削除する、**判断**図形を削除するをクリックする分岐を右クリックして**削除**、またはキーを押してルール分岐を選択、**削除**キー。