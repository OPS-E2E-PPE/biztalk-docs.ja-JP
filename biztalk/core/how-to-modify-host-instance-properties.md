---
title: ホスト インスタンスのプロパティを変更する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a35ca0c8-89b3-483a-b2fc-c8f43a8864d1
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 859170362ce804db6eff5b0e928998f008d0c2c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255154"
---
# <a name="update-host-instance-properties"></a>ホスト インスタンスのプロパティを更新します。

## <a name="overview"></a>概要
BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、ホスト インスタンスに変更を加えることができます。 ホスト インスタンスを実行しているサービス アカウントを変更したり、ホスト インスタンスを無効にできます。 ホスト インスタンスを無効にすることもできます。 たとえば、ホスト インスタンスの設定を維持する必要があるが、インスタンスを起動しないようにする必要がある場合は、インスタンスを無効にできます。 ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)です。  
  
 信頼済みホストのホスト インスタンスと信頼されていないホストのホスト インスタンスで同じサービス アカウントを使用することはできません。 ホスト インスタンスの信頼設定を変更し、ホスト インスタンスで他のホスト インスタンスが使用しているサービス アカウントを使用する必要がある場合は、次のいずれかを実行できます。  
  
-   信頼設定を新しいサービス アカウントに変更するホスト インスタンスのサービス アカウントを変更できます。  
  
-   ホスト インスタンスのサービス アカウントを、同じ信頼設定の他のホスト インスタンスで使用する既存のサービス アカウントに変更できます。  
  
-   ホスト インスタンスを削除し、別の信頼設定とサービス アカウントを使用するホスト インスタンスを再作成できます。  
  
> [!CAUTION]
>  ホスト インスタンスのプロパティを更新して、ホスト インスタンスの資格情報を変更する必要があります。 サービスに対応する資格情報を変更する場合、ホスト インスタンスに対して指定するサービス アカウントは、そのホスト上のグループのメンバーである必要があります。 サービス スナップインまたはコンピューターの管理コンソールを使用してホストの資格情報を変更してはいけません。ホスト インスタンスが正常に動作しなくなることがあります。  
  
> [!CAUTION]
>  ホスト インスタンスの資格情報を変更する場合は、対応する SQL Server の資格情報も変更する必要があります。 SQL Server の資格情報を更新しないと、ホスト インスタンスは正常に動作しません。  
  
 WMI を使用してホスト インスタンスを変更する方法の詳細については、次を参照してください。 **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
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
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、クリックして**ホスト インスタンス**です。  
  
3.  詳細ウィンドウで、変更、およびをクリックするホスト インスタンスを右クリックして**プロパティ**です。  
  
4.  **ホスト インスタンスのプロパティ**ダイアログ ボックスで、をクリックして**構成**サービス アカウント情報を変更します。  
  
5.  **ログオン資格情報** ダイアログ ボックスで、アカウント名とするホスト インスタンスが実行、およびをクリックし、アカウントのパスワードを入力**OK**です。  
  
6.  **ホスト インスタンスのプロパティ**ダイアログ ボックスで、次のように行い、クリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ホスト名**|選択したサーバーに関連付けられているホストの名前を表示します。|  
    |**[サーバー]**|選択したホストに関連付けられているサーバーを表示します。|  
    |**ログオン**|ホスト インスタンスを実行する、新しいサービス アカウントのアカウント名を表示します。|  
    |**構成**|クリックすると表示、**ログオン資格情報**ダイアログ ボックスで、アカウント名とホスト インスタンスを実行するアカウントのパスワードを入力できます。|  
    |**ホスト インスタンスの開始を無効にします。**|選択したホストの状態を有効から無効に変更する場合、このチェック ボックスをオンにします。 ホスト インスタンスを開始せずに設定を保持する場合は、インスタンスを無効にすると便利です。|  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスを管理します。](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト インスタンスを追加します。](../core/how-to-add-a-host-instance.md)   
 [ホスト インスタンスを開始します。](../core/how-to-start-a-host-instance.md)   
 [ホスト インスタンスを停止します。](../core/how-to-stop-a-host-instance.md)   
 [ホスト インスタンスを削除します。](../core/how-to-delete-a-host-instance.md)