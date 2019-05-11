---
title: 手順 3:構成し、アプリケーションを起動します |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dd0d569355d0873b42bc708b44e12993e97f58e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367704"
---
# <a name="step-3-configure-and-start-the-application"></a>手順 3:構成し、アプリケーションを起動します
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、構成し、SampleApplication アプリケーションを起動します。 作成した論理アイテムを関連付ける SampleApplication アプリケーションを構成するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]物理対応します。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 2。ポートを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)します。  
  
### <a name="to-configure-and-start-the-application"></a>構成して、アプリケーションを起動するには  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. 左側にあるコンソール ツリーで [ **BizTalk Server 管理**を右クリックして**BizTalk グループ**、] をクリックし、**更新**します。  
  
3. 展開**BizTalk グループ**、展開**アプリケーション**、右クリックして**SampleApplication**、順にクリックします**構成**します。  
  
4. **アプリケーションの構成** ダイアログ ボックスで、 **EmployeeOrch**  タブで、次の操作を行います。  
  
   1.  **ホスト**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
   2.  セルをダブルクリックして**ReceiveNotification**選択**NotifyReceivePort**ドロップダウン リストから。  
  
   3.  セルをダブルクリックして**SQLOutboundPort**選択**SQLOutboundPort**ドロップダウン リストから。  
  
   4.  セルをダブルクリックして**SaveResponsePort**選択**EmailResponse**ドロップダウン リストから。  
  
5. 次の図は、構成されたアプリケーションを示します。  
  
    ![アプリケーションが構成されている](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")  
  
6. **アプリケーションの構成**ダイアログ ボックスで、をクリックして**OK**します。  
  
7. コンソール ツリーで、右クリック**SampleApplication**、 をクリックし、**開始**します。  
  
8. コンソール ツリーで、クリックして**アプリケーション**します。  
  
9. アプリケーションの詳細ペインでいることを確認、**状態**の**SampleApplication**は**開始**します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 構成を SampleApplication アプリケーションを開始します。  
  
## <a name="next-steps"></a>次の手順  
 新しく加わる従業員を挿入して、アプリケーションをテストする、**従業員**」の説明に従って、テーブル[手順 4。アプリケーションをテストする](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 2:ポートを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)   
 [手順 4:アプリケーションをテストします。](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)   
 [レッスン 5: ソリューションを展開する](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)