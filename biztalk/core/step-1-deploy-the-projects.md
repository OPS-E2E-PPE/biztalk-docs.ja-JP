---
title: '手順 1: プロジェクトの配置 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0467c140-1f4c-4cfa-b46f-dc1d0f8755d4
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b25af8ee1095a5365fabd955f7185acbc79254db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007555"
---
# <a name="step-1-deploy-the-projects"></a>ステップ 1: プロジェクトの配置
![ステップ 1/3](../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、EAISchemas および EAIOrchestration プロジェクトを展開します。  
  
 **目的:** アセンブリが自動的に構築され、指定したアプリケーションに展開されているプロジェクトまたは Visual Studio でソリューションを展開するときにします。 このプロセスの一部として、アセンブリは、アセンブリに含まれるオーケストレーション、スキーマ、およびマップ (これらは "アイテム" と呼ばれます) と共にローカルの BizTalk 管理データベースにインポートされ、データベース内で指定したアプリケーションに関連付けられます。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
- [レッスン 1: スキーマおよびマップの定義](../core/lesson-1-define-schemas-and-a-map.md)  
  
- [レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)  
  
- メンバーとしてサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループ

- Visual Studio を管理者特権で実行します。

> [!TIP]
> 必要なチュートリアル ファイルをダウンロードする[チュートリアル 1: エンタープライズ アプリケーション統合](https://www.microsoft.com/download/details.aspx?id=22793)します。

## <a name="open-the-solution-with-administrative-rights"></a>管理者権限を持つソリューションを開きます  
  
1. BizTalk Server 管理者グループのメンバーとして Windows にサインインします。  
  
2. 開始**Microsoft Visual Studio**に管理者として。  
  
3. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューで、**オープン**、] をクリックし、**プロジェクト/ソリューション**。  
  
4. **プロジェクトを開く** ダイアログ ボックスを参照、 **EAISolution.sln**プロジェクト ソリューション ファイル、およびクリックして**オープン**します。  
  
   展開プロセスでは、アセンブリが厳密に署名されている必要があります。  アセンブリに署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付ける必要があります。  このファイルは、チュートリアル ファイルに含まれます。  
  
   BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションの展開、管理、およびトラブルシューティングをすばやく簡単に行えるようにする BizTalk Server の機能です。 BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションで使用される "アイテム" の論理グループです。 プロジェクトのアプリケーション名を指定できます。  展開プロセスには、存在しない場合は、指定の名前を持つ新しいアプリケーションを自動的に作成されます。  
  
## <a name="configure-and-deploy-the-projects"></a>構成し、プロジェクトの配置  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをクリックして**プロパティ**します。  
  
2.  をクリックして、**署名**] タブで [**アセンブリに署名**します。  
  
3.  ドロップダウン リストから、**厳密な名前キー ファイルを選択して**ボックスで、 **\<を参照しています.\>**.  
  
4.  **ファイルの選択** ダイアログ ボックスに移動**C:\BTStutorials**、 をクリックして**btstutorials.snk**、順にクリックします**オープン**します。 
  
5.  をクリックして、**展開**タブの右側にボックスで、**アプリケーション名**、型`EAISolution`します。  
  
6.  ボックスの右側にドロップダウン リストから**再デプロイ**を選択します**True**します。  
  
7.  ソリューション エクスプ ローラーで右クリックして**EAISchemas**、 をクリックし、**デプロイ**します。  出力ウィンドウが表示されます。  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
8.  手順 1 ~ 7 EAIOrchestration プロジェクトを配置する.  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 このステップでは、EAISchemas プロジェクトおよび EAIOrchestration プロジェクトを配置しました。  
  
## <a name="next-steps"></a>次の手順  
 物理ポートを作成し、オーケストレーションの論理ポートにバインドします。  
  
 [手順 2: 構成し、アプリケーションを起動します](../core/step-2-configure-and-start-the-application1.md)   
 [手順 3: ソリューションのテスト](../core/step-3-test-the-solution2.md)
