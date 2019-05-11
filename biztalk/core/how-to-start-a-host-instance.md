---
title: ホスト インスタンスの開始 |Microsoft Docs
description: BizTalk 管理コンソールを使用して、BizTalk Server でホスト インスタンスを開始するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96a4362-2147-4b8e-a270-bf9a17477ba3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dc17eec6a1782a1b607be812003978793d49c6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383834"
---
# <a name="start-a-host-instance"></a>ホスト インスタンスを開始します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、ホスト インスタンスを開始できます。 ホスト インスタンスを追加または停止したら、インスタンスを開始し、実行して、メッセージがメッセージ ボックス データベースにルーティングされるようにする必要があります。  
  
> [!IMPORTANT]
>  ホスト インスタンスに指定するサービス アカウントは、関連するホストの Windows グループのメンバーである必要があります。 それ以外の場合、ホスト インスタンスには、実行時に適切なアクセス許可または認証がない可能性があります。 また、セキュリティ上の理由により、ホスト インスタンスでホストされているオーケストレーションが悪意のあるカスタム コードを実行する可能性があるため、アカウントには、最小限の特権を付与する必要があります。  
  
 ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)します。 WMI を使用して、ホスト インスタンスを開始する方法については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
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
  
3. 詳細ペインで、起動し、クリックするホスト インスタンスを右クリックして**開始**します。  
  
    ホスト インスタンスの状態に変わる**開始待ち**します。 ホスト インスタンスの起動状態に変わります**を実行している**します。  
  
   ホスト インスタンスを開始後、インスタンスを停止して、メッセージがメッセージ ボックス データベースにルーティングされないようにすることができます。 特定のコンピューターから BizTalk Server を削除する前に、ホスト インスタンスを停止する必要があります。 ホスト インスタンスの停止については、次を参照してください。[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト インスタンスを追加します。](../core/how-to-add-a-host-instance.md)   
 [ホスト インスタンスを停止します。](../core/how-to-stop-a-host-instance.md)   
 [ホスト インスタンスを削除します。](../core/how-to-delete-a-host-instance.md)   
 [ホスト インスタンスのプロパティを変更します。](../core/how-to-modify-host-instance-properties.md)