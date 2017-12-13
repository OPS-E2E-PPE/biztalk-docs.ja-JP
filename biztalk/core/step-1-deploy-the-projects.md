---
title: "手順 1: 配置プロジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: "44"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad4424327f6cd24624abe6b4a850f3c24153e6a4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-deploy-the-projects"></a>ステップ 1: プロジェクトの配置
![手順 1/3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:** EAISchemas および EAIOrchestration プロジェクトを配置するこの手順でします。  
  
 **目的:**プロジェクトまたは Visual Studio でソリューションを展開するときに、アセンブリに自動的に構築され、指定されたアプリケーションに展開します。 このプロセスの一部として、アセンブリは、アセンブリに含まれるオーケストレーション、スキーマ、およびマップ (これらは "アイテム" と呼ばれます) と共にローカルの BizTalk 管理データベースにインポートされ、データベース内で指定したアプリケーションに関連付けられます。  
  
## <a name="prerequisites"></a>前提条件  
  
-   [レッスン 1: スキーマおよびマップの定義](../core/lesson-1-define-schemas-and-a-map.md)  
  
-   [レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)  
  
-   メンバーとしてサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループ

-   管理者特権で Visual Studio を実行します。

> [!TIP]
> 必要なチュートリアル ファイルをダウンロードする[チュートリアル 1: エンタープライズ アプリケーション統合](https://www.microsoft.com/download/details.aspx?id=22793)です。

## <a name="open-the-solution-with-administrative-rights"></a>管理者権限を持つソリューションを開きます  
  
1.  BizTalk Server 管理者グループのメンバーとして Windows にサインインします。  
  
2.  開始**Microsoft Visual Studio**を管理者として。  
  
3.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**開く**、クリックして**プロジェクト/ソリューション**です。  
  
4.  **プロジェクトを開く** ダイアログ ボックスを参照、 **EAISolution.sln**プロジェクト ソリューション ファイルをクリックして**開く**です。  
  
 展開プロセスでは、アセンブリが厳密に署名されている必要があります。  アセンブリに署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付ける必要があります。  このファイルは、チュートリアル ファイルに含まれます。  
  
 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。 プロジェクトのアプリケーション名を指定できます。  展開プロセスが存在しない場合は、指定された名前を持つ新しいアプリケーションが自動的に作成されます。  
  
## <a name="configure-and-deploy-the-projects"></a>構成し、プロジェクトの配置  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをクリックして**プロパティ**です。  
  
2.  クリックして、**署名**] タブで [**アセンブリに署名**です。  
  
3.  ドロップダウン リストから、**厳密な名前キー ファイルを選択して**ボックスで、 **\<を参照しています...\>**.  
  
4.  **ファイルの選択** ダイアログ ボックスに移動**C:\BTStutorials**、 をクリックして**btstutorials.snk**、クリックして**開く**です。 
  
5.  クリックして、**展開** タブで、ボックスの右側に**アプリケーション名**、型`EAISolution`です。  
  
6.  ボックスの右側にドロップダウン リストから**再展開** **True**です。  
  
7.  ソリューション エクスプ ローラーで右クリック**EAISchemas**、クリックして**展開**です。  出力ウィンドウが表示されます。  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  手順 1. ~ 7. EAIOrchestration プロジェクトを配置する.  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、EAISchemas プロジェクトおよび EAIOrchestration プロジェクトを配置しました。  
  
## <a name="next-steps"></a>次の手順  
 物理ポートを作成し、オーケストレーションの論理ポートにバインドします。  
  
 [手順 2: を構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md)   
 [手順 3: ソリューションのテスト](../core/step-3-test-the-solution2.md)
