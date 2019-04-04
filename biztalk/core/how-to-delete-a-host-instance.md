---
title: ホスト インスタンスの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35a06480-0962-4bdc-add2-56f979a2f1c9
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ecc7999e807b4036f80e8fdd1941d447f7af163
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023584"
---
# <a name="delete-a-host-instance"></a>ホスト インスタンスを削除します。

## <a name="overview"></a>概要
使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは Windows Management Instrumentation (WMI) ホスト インスタンスを削除します。 ホスト インスタンスの詳細については、[ホスト インスタンス](../core/host-instances.md)を参照してください。 WMI を使用して、ホスト インスタンスを削除する方法の詳細については、**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。
  
 ホスト インスタンスを削除すると、BizTalk Server ランタイムのインスタンスが、関連付けられたサーバーから削除されます。また、BizTalk 管理データベースが、ホストからそのインスタンスを削除するように更新されます。  
  
 ホスト インスタンスを削除したときにメッセージが失われることのないように、BizTalk Server では、インスタンスが実際に削除される前にすべての処理を完了します。  
  
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
  
3. 詳細ペインで、削除、およびクリックするホスト インスタンスを右クリックして**削除**します。  
  
4. **ホスト インスタンスの削除確認**ダイアログ ボックスで、をクリックして **[はい]** します。  
  
   > [!NOTE]
   >  BizTalk Server でホスト インスタンスを削除できない場合は、別のダイアログ ボックスが表示され、ホスト インスタンスを強制的に削除できます。 提供される情報を読むには、次のようにクリックします。**はい**ホスト インスタンスを削除します。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)   
 [ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)   
 [ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)   
 [ホスト インスタンスのプロパティを変更する方法](../core/how-to-modify-host-instance-properties.md)