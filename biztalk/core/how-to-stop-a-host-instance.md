---
title: ホスト インスタンスの停止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1f2e0c1-a387-4182-82ef-e25f49ac509b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b66c89ccafa72c56de00aebd24091915643f44e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972675"
---
# <a name="stop-a-host-instance"></a>ホスト インスタンスを停止します。

## <a name="overview"></a>概要
使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは Windows Management Instrumentation (WMI) をホスト インスタンスを停止します。 コンピューターからホスト インスタンスまたは BizTalk Server を削除する前に、ホスト インスタンスを停止する必要があります。 インストールされ、開始しているホスト インスタンスを停止できます。 ホスト インスタンスの詳細については、[ホスト インスタンス](../core/host-instances.md)を参照してください。  
  
 WMI を使用して、ホスト インスタンスを停止する方法の詳細については、**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
 また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。  
  
-   BAM プライマリ インポート (BAMPrimaryImport)  
  
-   BizTalk 管理 (BizTalkMgmtDb)  
  
-   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)  
  
-   BizTalk 追跡 (BizTalk DTADb)  
  
-   ルール エンジン (BizTalkRuleEngineDb)  
  
> [!CAUTION]
>  ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。 これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。  
  
## <a name="steps"></a>手順
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**BizTalk グループ、をクリックして**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。  
  
3. 詳細ペインで、停止、およびクリックするホスト インスタンスを右クリックして**停止**します。  
  
    ホスト インスタンスの状態に変わる**Stopped**します。  
  
   ホスト インスタンスを開始または削除するか、コンピューターから BizTalk Server を削除する場合、まず、ホスト インスタンスを停止する必要があります。 ホスト インスタンスの開始方法の詳細については、[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)を参照してください。 ホスト インスタンスの削除方法の詳細については、[ホスト インスタンスを削除する方法](../core/how-to-delete-a-host-instance.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)   
 [ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)   
 [ホスト インスタンスを削除する方法](../core/how-to-delete-a-host-instance.md)   
 [ホスト インスタンスのプロパティを変更する方法](../core/how-to-modify-host-instance-properties.md)