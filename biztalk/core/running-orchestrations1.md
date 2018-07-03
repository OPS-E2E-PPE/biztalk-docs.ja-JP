---
title: Orchestrations1 を実行している |。Microsoft Docs
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
- host instances, stopping and restarting
- orchestrations, compiling
- orchestrations, deploying
ms.assetid: b992bdba-630d-4f28-aca8-c568f3c27968
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe1645ecaff4cea4f153c988188fa7f47e94959c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969123"
---
# <a name="running-orchestrations"></a>オーケストレーションの実行
次の手順では、オーケストレーションのビルド、展開、バインド、および開始の方法について説明します。  
  
## <a name="creating-a-strong-name-key"></a>厳密な名前キーを作成します。  
  
#### <a name="to-create-a-strong-name-key"></a>厳密な名前のキーを作成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトを起動します。  
  
2. たとえば、既存のプロジェクトにディレクトリを変更\<ドライブ\>: \Adapter_Install\biztalk2010\my_project します。  
  
3. コマンド プロンプトで、次を入力し、ENTER キーを押します。  
  
    `sn -k SSOSchedule.snk`  
  
## <a name="compiling-and-deploying-an-orchestration"></a>オーケストレーションのコンパイルおよび展開  
  
#### <a name="to-compile-and-deploy-an-orchestration"></a>オーケストレーションをコンパイルおよび展開するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、[ssoschedule] プロジェクトを右クリックし、選択**プロパティ**します。  
  
2. クリックして**共通プロパティ**、展開、**アセンブリ**ノード。  
  
3. SSOSchedule.snk のパスを入力、**アセンブリ キー ファイル**テキスト ボックス。  
  
4. Configuration properties \deployment\server にドット (.) または、コンピューター名が含まれていることを確認し、クリックして**OK**します。  
  
5. ソリューション エクスプ ローラーで右クリックして**ssoschedule**、 をクリック**リビルド**します。  
  
6. 右クリックし、 **ssoschedule**、 をクリック**デプロイ**します。  
  
## <a name="starting-the-orchestration"></a>オーケストレーションの開始  
  
#### <a name="to-start-the-orchestration"></a>オーケストレーションを開始するには  
  
1.  BizTalk 管理コンソールで、開始するオーケストレーションを選択します。  
  
2.  オーケストレーションを右クリックし、をクリックして**開始**します。  
  
## <a name="stopping-and-restarting-a-host-instance"></a>停止して、ホスト インスタンスの再起動  
 サンプルを展開したら、ホスト インスタンスを再起動する必要があります。  
  
#### <a name="to-stop-and-restart-a-host-instance"></a>ホスト インスタンスを停止して再起動するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]を選択し、 **BizTalk Server 管理コンソール。**  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをダブルクリック、 **Microsoft BizTalk Server (ローカル)** ノード展開**ホスト**します。  
  
3. 左側のウィンドウで、選択、 **BizTalkServerApplication**します。  
  
4. 右側のウィンドウでホスト インスタンス (たとえば、コンピューター名) を右クリックし、をクリックして**停止**します。  
  
    ホスト インスタンスの状態に変わる**Stopped**します。  
  
5. 右側のウィンドウで、ホスト インスタンスを右クリックし、をクリックして**開始**します。  
  
    ホスト インスタンスの状態に変わる**開始待ち**します。  
  
    状態を変更する**を実行している**、 をクリックして**更新**、またはホスト インスタンスを右クリックし、をクリックし、**更新**します。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)