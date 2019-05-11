---
title: 手順 1:EAISchemas プロジェクトの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a14ee61-fa27-4f03-997e-42c34a77afee
caps.latest.revision: 55
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d82e9336cd16801af07fca419a4b0502843994
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392864"
---
# <a name="step-1-create-eaischemas-project"></a>手順 1:EAISchemas プロジェクトを作成します。
![手順 5 の 1](../core/media/step-1of5.gif "Step_1of5")  

 **所要時間:** 5 分  

 **目標:** この手順で作成する新しい[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューションとプロジェクト。  

 **目的:** 一部またはすべてを作成する BizTalk プロジェクト システムを使用して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]アプリケーションやビジネス ソリューションです。 ソリューションの中核となる要素は、スキーマ、オーケストレーション、Web メッセージの種類、クラス、パイプライン、マップ、参照などの項目の集合である BizTalk プロジェクトです。ユーザーは、これらの項目をビルドしてアセンブリを生成し、生成したアセンブリを展開します。  

## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  

-   この手順を開始する前に、手順を完了する必要があります[チュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md)します。  

## <a name="procedures"></a>手順  

#### <a name="to-create-a-new-visual-studio-solutionproject"></a>新しい Visual Studio ソリューション/プロジェクトを作成するには  

1. 開始**Microsoft Visual Studio**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  

3. **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  


   |             プロパティ              |                                目的                                |
   |-----------------------------------|--------------------------------------------------------------------------|
   |      **インストール済みテンプレート**      | クリックして**BizTalk プロジェクト**、 をクリックし、**空の BizTalk Server プロジェクト**します。 |
   |             **名前**              |                           型**EAISchemas**します。                           |
   |           **場所**            |                      型**C:\tutorial\Lessons**します。                       |
   |         **[ソリューション名]**         |                          型**EAISolution**します。                           |
   | **ソリューションのディレクトリを作成します。** |                                (選択)                                |


4. **[OK]** をクリックします。  

5. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  

## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、新しいプロジェクトを開いて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  

## <a name="next-steps"></a>次の手順  
 在庫補充要求メッセージのスキーマを作成します。  

## <a name="see-also"></a>参照  
 [このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md)   
 [手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)   
 [ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)   
 [手順 4:マップを作成します。](../core/step-4-create-the-map.md)   
 [手順 5:EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)   
 [開発者ツール](../core/developer-tools.md)   
 [BizTalk プロジェクトの操作](../core/working-with-biztalk-projects.md)