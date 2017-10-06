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
ms.openlocfilehash: eb4262b2bb424a339f866f3b4a14ae03c2e507f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-deploy-the-projects"></a>ステップ 1: プロジェクトの配置
![手順 1/3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:** EAISchemas および EAIOrchestration プロジェクトを配置するこの手順でします。  
  
 **目的:**プロジェクトまたは Visual Studio でソリューションを展開するときに、アセンブリに自動的に構築され、指定されたアプリケーションに展開します。 このプロセスの一部として、アセンブリは、アセンブリに含まれるオーケストレーション、スキーマ、およびマップ (これらは "アイテム" と呼ばれます) と共にローカルの BizTalk 管理データベースにインポートされ、データベース内で指定したアプリケーションに関連付けられます。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   このステップを開始する前に、次のレッスンを完了しておく必要があります。  
  
    -   [レッスン 1: 定義のスキーマとマップ](../core/lesson-1-define-schemas-and-a-map.md)  
  
    -   [レッスン 2: ビジネス プロセスを定義します。](../core/lesson-2-define-the-business-process.md)  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。  
  
-   ユーザー アカウント制御 (UAC) をサポートするシステムでは、Visual Studio を管理者特権で実行する必要があります。  
  
## <a name="procedures"></a>手順  
 Visual Studio を使用してアプリケーションを展開するには、BizTalk Server 管理者グループのメンバーとして Windows にログオンして Visual Studio を管理者として実行します。  そのようにしない場合は、"アクセスは拒否されました" というエラーが表示されます。  
  
#### <a name="to-open-the-solution-with-administrative-privileges"></a>管理特権でソリューションを開くには  
  
1.  BizTalk Server 管理者グループのメンバーとして Windows にログオンします。  
  
2.  開始**Microsoft Visual Studio**を管理者として。  
  
3.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**開く**、クリックして**プロジェクト/ソリューション**です。  
  
4.  **プロジェクトを開く** ダイアログ ボックスを参照、 **EAISolution.sln**プロジェクト ソリューション ファイルをクリックして**開く**です。  
  
 展開プロセスでは、アセンブリが厳密に署名されている必要があります。  アセンブリに署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付ける必要があります。  このファイルは、チュートリアル ファイルによって提供されます。  
  
 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。 プロジェクトのアプリケーション名を指定できます。  展開プロセスでは、指定された名前を持つアプリケーションが存在しない場合、その新しいアプリケーションが自動的に作成されます。  
  
#### <a name="to-configure-and-deploy-the-projects"></a>プロジェクトを構成して展開するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをクリックして**プロパティ**です。  
  
2.  クリックして、**署名**] タブで [**アセンブリに署名**です。  
  
3.  ドロップダウン リストから、**厳密な名前キー ファイルを選択して**ボックスで、  **\<[参照...] >**です。  
  
4.  **ファイルの選択** ダイアログ ボックスに移動**C:\BTStutorials**、 をクリックして**btstutorials.snk**、クリックして**開く**です。  
  
5.  クリックして、**展開** タブで、ボックスの右側に**アプリケーション名**、型`EAISolution`です。  
  
6.  ボックスの右側にドロップダウン リストから**再展開** **True**です。  
  
7.  ソリューション エクスプ ローラーで右クリック**EAISchemas**、クリックして**展開**です。  出力ウィンドウが表示されます。  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  手順 1. ～ 7. を繰り返して、EAIOrchestration プロジェクトを展開します。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、EAISchemas プロジェクトおよび EAIOrchestration プロジェクトを配置しました。  
  
## <a name="next-steps"></a>次の手順  
 物理ポートを作成し、オーケストレーションの論理ポートにバインドします。  
  
## <a name="see-also"></a>参照  
 [手順 2: を構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md)   
 [手順 3: ソリューションをテストします。](../core/step-3-test-the-solution2.md)