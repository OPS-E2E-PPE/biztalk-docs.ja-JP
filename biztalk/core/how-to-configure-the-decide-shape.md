---
title: 判断図形を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: a22368134e2c1a0d8deb277e186792158a7c2dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248690"
---
# <a name="how-to-configure-the-decide-shape"></a>判断図形を構成する方法
![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")  
判断図形  
  
 各分岐、**判断**図形を除く、 **else**分岐、ルールに関連付けられていること。 個々の分岐の実行のために評価されるルール内のブール式は、BizTalk 式エディターを使用して作成できます。 **Else**ブランチ直前の分岐にブール式の否定を意味する、関連付けられている式がないです。  
  
 規則の下または**else**句、支店、**判断**図形がオーケストレーションの他の部分と同じように、追加の図形を含めることができます。  
  
### <a name="to-configure-a-decide-shape"></a>判断図形を構成するには  
  
1.  BizTalk 式エディターが表示されていない場合は、ルールを右クリックし、をクリックして**ブール式の編集**は、[プロパティ] ウィンドウで、**省略記号**(**.**) ボタンをクリックして、**式**プロパティです。  
  
2.  BizTalk 式エディターでは、以外の各分岐のブール式を作成、 **Else**分岐します。 例を次に示します。  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a>判断図形に分岐を追加するには  
  
1.  右クリックし、**判断**図形をクリックして**新しいルール分岐**です。  
  
     - または -  
  
2.  新しい図形を既存の 2 つの分岐の間にドラッグします。  
  
    > [!NOTE]
    >  分岐を削除する、**判断**図形をクリックして、削除する分岐を右クリックして**削除**、ルール分岐とキーを押すか、選択、**削除**キー。