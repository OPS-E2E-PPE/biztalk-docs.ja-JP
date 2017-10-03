---
title: "手順 3: を構成し、アプリケーションを起動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96f26035094ee6e39b672b480525747f8aaf4ede
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-and-start-the-application"></a>手順 3: を構成し、アプリケーションを起動
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 10 分  
  
 **目標:**この手順で構成して SampleApplication アプリケーションを起動します。 作成した論理アイテムに関連付ける SampleApplication アプリケーションを構成するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]物理対応するとします。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 2: ポートを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)です。  
  
### <a name="to-configure-and-start-the-application"></a>構成し、アプリケーションの起動  
  
1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
2.  コンソール ツリーで、左側で、展開**BizTalk Server 管理コンソール**を右クリックして**BizTalk グループ**、順にクリック**更新**です。  
  
3.  展開**BizTalk グループ**、展開**アプリケーション**を右クリックして**SampleApplication**をクリックし、**構成**です。  
  
4.  **アプリケーションの構成** ダイアログ ボックスで、 **EmployeeOrch**  タブで、次の操作します。  
  
    1.  **ホスト**ドロップダウン リストで、 **BizTalkServerApplication**です。  
  
    2.  全体でセルをダブルクリックして**ReceiveNotification**選択**NotifyReceivePort**ドロップダウン リストからです。  
  
    3.  全体でセルをダブルクリックして**SQLOutboundPort**選択**SQLOutboundPort**ドロップダウン リストからです。  
  
    4.  全体でセルをダブルクリックして**SaveResponsePort**選択**EmailResponse**ドロップダウン リストからです。  
  
5.  次の図は、構成されたアプリケーションを示します。  
  
     ![アプリケーションの構成](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")  
  
6.  **アプリケーションの構成**ダイアログ ボックスで、をクリックして**OK**です。  
  
7.  コンソール ツリーを右クリックして**SampleApplication**、クリックして**開始**です。  
  
8.  コンソール ツリーでクリックして**アプリケーション**です。  
  
9. アプリケーションの詳細ウィンドウで、ことを確認、**ステータス**の**SampleApplication**は**Started**です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 構成および SampleApplication アプリケーションを開始します。  
  
## <a name="next-steps"></a>次の手順  
 新しい従業員を挿入することで、アプリケーションをテストする、**従業員**」の説明に従っての表に、[手順 4: アプリケーションをテストする](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 2: ポートを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)   
 [手順 4: アプリケーションをテストします。](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)   
 [レッスン 5: ソリューションを配置します。](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)