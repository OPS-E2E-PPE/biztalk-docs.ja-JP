---
title: "手順 3: 要求拒否スキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1ce166c-1be1-4ef4-9d00-3da7038d4ada
caps.latest.revision: "39"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff343c58e836bc0738f0200016308eb7a4d90b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-the-request-decline-schema"></a>ステップ 3: 要求拒否スキーマの作成
![手順 5 の 3](../core/media/step-3of5.gif "Step_3of5")  
  
 **所要時間:** 7 分  
  
 **目標:**メッセージのスキーマを作成するこの手順で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス プロセスで在庫補充要求を拒否した場合は、倉庫に返送します。  
  
 **目的:**スキーマ、データと要求拒否メッセージの構造を定義します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、メッセージ内のデータの識別と操作にスキーマが使用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 1: EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)です。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-create-the-request-decline-schema"></a>要求拒否スキーマを作成するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  **新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストールされたテンプレート**|をクリックして**スキーマ ファイル**、クリックして**スキーマ**です。|  
    |**名前**|「`RequestDecline.xsd`.|  
  
3.  **[追加]**をクリックします。  
  
4.  BizTalk エディターで、スキーマ ツリーからをクリックして、**ルート**ノードをオンにします。  
  
5.  値を変更、プロパティ ペインで、**ノード名**プロパティを`DeclineReq`、ENTER キーを押します。  
  
6.  スキーマ ツリー内を右クリックし、 **DeclineReq**に**スキーマ ノードの挿入**、順にクリック**子フィールド要素**です。  
  
7.  型`ReqID`要素、およびし、ENTER キーを押して新しい名前として。  
  
8.  という 2 つ目の子フィールド要素を追加`GrandTotal`です。  
  
9. **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、ビジネス プロセスで在庫要求が拒否された場合に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から倉庫に返されるメッセージ用のスキーマを作成しました。  
  
## <a name="next-steps"></a>次の手順  
 要求メッセージの形式を変更して要求拒否メッセージを作成するためのオーケストレーションに必要なマップを作成します。  
  
## <a name="see-also"></a>参照  
 [手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)  
 [手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)   
 [手順 4: マップを作成します。](../core/step-4-create-the-map.md)   
 [手順 5: EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)   
 [BizTalk エディターを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-editor.md)