---
title: Orchestrations2 を実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strong name keys, creating
- orchestrations
- creating strong name keys
- compiling orchestrations
- host instances, stopping and restarting
- deployment, orchestrations
- orchestrations, compiling
- orchestrations, deploying
- stopping host instances
- restarting host instances
ms.assetid: a098d552-d302-44f6-9af9-d77d16549fd3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c43c0694397f024b692012f7e2846e6ff38bbd14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254517"
---
# <a name="running-orchestrations"></a>オーケストレーションの実行
次の手順では、構築、展開、バインド、およびオーケストレーションを開始する方法について説明します。  
  
## <a name="creating-a-strong-name-key"></a>厳密な名前キーを作成します。  
  
#### <a name="to-create-a-strong-name-key"></a>厳密な名前キーを作成するには  
  
1. 開く、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプト。  
  
2. 既存のプロジェクトにディレクトリを変更し、ENTER キーを押します。  
  
    以下に例を示します。  
  
    **\<drive\>:\Adapter_Install\biztalk\my_project**  
  
3. コマンド プロンプトで、次を入力し、ENTER キーを押します。  
  
    `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a>コンパイルして、オーケストレーションの展開  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a>コンパイルして、オーケストレーションを展開するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーを右クリックし、 **[ssoschedule]** 順に選択して、**プロパティ**します。  
  
2. クリックして**共通プロパティ**、展開、**アセンブリ**ノード。  
  
3. SSOSchedule.snk のパスを入力、**アセンブリ キー ファイル**テキスト ボックス。  
  
4. Configuration properties \deployment\server がドット (.) または、コンピューター名であることを確認し、をクリックし、 **OK**します。  
  
5. ソリューション エクスプ ローラーで右クリック**ssoschedule**、 をクリックし、**リビルド**します。  
  
6. 右クリック**ssoschedule**、 をクリックし、**デプロイ**します。  
  
## <a name="starting-the-orchestration"></a>オーケストレーションの開始  
  
#### <a name="to-start-the-orchestration"></a>オーケストレーションを開始するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理コンソール。**  
  
2. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション、およびクリック**オーケストレーション**します。  
  
3. 詳細ペインで、オーケストレーションを右クリックし、をクリックして**開始**します。  
  
## <a name="stopping-and-restarting-a-host-instance"></a>停止して、ホスト インスタンスの再起動  
 サンプルをデプロイした後は、ホスト インスタンスを再起動する必要があります。  
  
#### <a name="to-stop-and-restart-a-host-instance"></a>停止して、ホスト インスタンスを再起動するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理コンソール。**  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**ホスト インスタンスの**します。  
  
3. 右側のウィンドウでホスト インスタンス (たとえば、コンピューター名) を右クリックし、をクリックして**停止**します。  
  
    ホスト インスタンスの状態に変わる**Stopped**します。  
  
4. 右側のウィンドウで、ホスト インスタンスを右クリックし、をクリックして**開始**します。  
  
    ホスト インスタンスの状態に変わる**開始待ち**します。  
  
    状態を変更する**を実行している** をクリック**更新**、またはホスト インスタンスを右クリックし、をクリックし、**更新**します。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)