---
title: 手順 3:要求拒否スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ce166c-1be1-4ef4-9d00-3da7038d4ada
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 039fd40448d2545e360c5599b1448c6bcbf9c6e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392649"
---
# <a name="step-3-create-the-request-decline-schema"></a>手順 3:要求拒否スキーマを作成します。
![手順 5 の 3](../core/media/step-3of5.gif "Step_3of5")  
  
 **所要時間:** 7 分  
  
 **目標:** この手順でメッセージのスキーマを作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス プロセスで在庫補充要求を拒否した場合は、倉庫に返送します。  
  
 **目的:** スキーマは、データと要求拒否メッセージの構造を定義します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] スキーマを使用して、メッセージ内のデータとの対話を識別します。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 1。EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)です。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-create-the-request-decline-schema"></a>要求拒否スキーマを作成するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  
  
2.  **新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストール済みテンプレート**|クリックして**スキーマ ファイル**、 をクリックし、**スキーマ**します。|  
    |**名前**|「`RequestDecline.xsd`.|  
  
3.  **[追加]** をクリックします。  
  
4.  BizTalk エディターでは、スキーマ ツリーからクリックして、**ルート**ノードを選択します。  
  
5.  プロパティ ペインでの値を変更、**ノード名**プロパティを`DeclineReq`、し、ENTER キーを押します。  
  
6.  スキーマ ツリーで、右クリックし、 **DeclineReq**に**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**します。  
  
7.  型`ReqID`要素、および、ENTER キーを押して新しい名前として。  
  
8.  という名前の 2 番目の子フィールド要素を追加`GrandTotal`します。  
  
9. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順で作成したメッセージのスキーマを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス プロセスで在庫要求が拒否された場合、倉庫に返送します。  
  
## <a name="next-steps"></a>次の手順  
 要求メッセージを再フォーマットして要求拒否メッセージを作成するオーケストレーションに必要なマップを作成します。  
  
## <a name="see-also"></a>参照  
 [ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)  
 [手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)   
 [手順 4:マップを作成します。](../core/step-4-create-the-map.md)   
 [手順 5:EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)   
 [BizTalk エディターを使用したスキーマの作成](../core/creating-schemas-using-biztalk-editor.md)