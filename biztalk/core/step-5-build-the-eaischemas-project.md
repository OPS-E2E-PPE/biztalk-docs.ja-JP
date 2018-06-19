---
title: '手順 5: EAISchemas プロジェクトのビルド |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20cd368-7446-4861-8d71-5bc25ce408a2
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394d9df78f7064df8501ed43149bd26793533c47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278154"
---
# <a name="step-5-build-the-eaischemas-project"></a>ステップ 5: EAISchemas プロジェクトのビルド
![手順 5 の 5](../core/media/step-5of5.gif "Step_5of5")  
  
 **所要時間:** 6 分  
  
 **目標:** この手順では、EAISchemas プロジェクトをコンパイルします。  
  
 **目的:** を Microsoft BizTalk Server と .NET Framework の最も重要な点はすべての BizTalk Server アイテム、マップやスキーマ、オーケストレーション、パイプライン、.NET アセンブリにコンパイルを取得します。 このしくみが意味するのは、これらのアセンブリに厳密な名前が必要であり、そのために .NET のバージョン管理規則にも従う必要が生じることです。 結果として、BizTalk のプロジェクトは、別の .NET プロジェクトまたはアセンブリ (BizTalk プロジェクトを含む) の特定のバージョンに対して構築されると、新しいバージョンに対して再構築されるまではそのバージョンを使い続けることになります。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   このステップを開始する前に、次のステップを完了しておく必要があります。  
  
    -   [手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)  
  
    -   [手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) 
  
    -   [手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)  
  
    -   [手順 4: マップを作成します。](../core/step-4-create-the-map.md)  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-build-the-eaischemas-project"></a>EAISchemas プロジェクトをビルドするには  
  
1.  ソリューション エクスプ ローラーで右クリック**EAISchemas**、クリックして**ビルド**です。  
  
     画面の下部に、次のように表示されます。  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ```  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、EAISchemas プロジェクトをビルドし、アセンブリ ファイル (DLL) を生成しました。  
  
## <a name="next-steps"></a>次の手順  
 承認条件を満たすには、在庫補充要求メッセージの内容を評価するビジネス プロセスを作成する[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)   
 [手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)   
 [手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)   
 [手順 4: マップを作成します。](../core/step-4-create-the-map.md)