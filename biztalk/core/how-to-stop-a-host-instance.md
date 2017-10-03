---
title: "ホスト インスタンスを停止 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1f2e0c1-a387-4182-82ef-e25f49ac509b
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 837b08c30263b48ad481c7e03820cfba0b6c0ecc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="stop-a-host-instance"></a>ホスト インスタンスを停止します。

## <a name="overview"></a>概要
使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは Windows Management Instrumentation (WMI) をホスト インスタンスを停止します。 コンピューターからホスト インスタンスまたは BizTalk Server を削除する前に、ホスト インスタンスを停止する必要があります。 インストールされ、開始しているホスト インスタンスを停止できます。 ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)です。  
  
 WMI を使用してホスト インスタンスを停止する方法については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
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
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループ、をクリックして**プラットフォームの設定**、順にクリック**ホスト インスタンス**です。  
  
3.  詳細ウィンドウで、停止、およびをクリックするホスト インスタンスを右クリックして**停止**です。  
  
     ホスト インスタンスの状態に変わる**Stopped**です。  
  
 ホスト インスタンスを開始または削除するか、コンピューターから BizTalk Server を削除する場合、まず、ホスト インスタンスを停止する必要があります。 ホスト インスタンスの開始方法の詳細については、次を参照してください。[ホスト インスタンスを起動する方法](../core/how-to-start-a-host-instance.md)です。 ホスト インスタンスを削除する方法の詳細については、次を参照してください。[ホスト インスタンスを削除する方法](../core/how-to-delete-a-host-instance.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)   
 [ホスト インスタンスを起動する方法](../core/how-to-start-a-host-instance.md)   
 [ホスト インスタンスを削除する方法](../core/how-to-delete-a-host-instance.md)   
 [ホスト インスタンスのプロパティを変更する方法](../core/how-to-modify-host-instance-properties.md)