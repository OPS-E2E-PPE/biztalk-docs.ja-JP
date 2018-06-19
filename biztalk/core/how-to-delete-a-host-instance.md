---
title: ホスト インスタンスを削除する |Microsoft ドキュメント
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
ms.openlocfilehash: 798ea341ef61b15729dd15742eef7701641e7547
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249202"
---
# <a name="delete-a-host-instance"></a>ホスト インスタンスを削除します。

## <a name="overview"></a>概要
使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは Windows Management Instrumentation (WMI) をホスト インスタンスを削除します。 ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)です。 WMI を使用してホスト インスタンスを削除する方法については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
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
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループ、をクリックして**プラットフォームの設定**、順にクリック**ホスト インスタンス**です。  
  
3.  詳細ウィンドウで、削除、およびをクリックするホスト インスタンスを右クリックして**削除**です。  
  
4.  **確認ホスト インスタンスの削除**ダイアログ ボックスで、をクリックして**はい**です。  
  
    > [!NOTE]
    >  BizTalk Server でホスト インスタンスを削除できない場合は、別のダイアログ ボックスが表示され、ホスト インスタンスを強制的に削除できます。 提供される内容を読み、をクリックして**はい**ホスト インスタンスを削除します。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)   
 [ホスト インスタンスを起動する方法](../core/how-to-start-a-host-instance.md)   
 [ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)   
 [ホスト インスタンスのプロパティを変更する方法](../core/how-to-modify-host-instance-properties.md)