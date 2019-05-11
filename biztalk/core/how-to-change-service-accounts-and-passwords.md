---
title: サービス アカウントとパスワードを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dff53d6b-c262-4b66-b822-1c61f54ae105
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d31db74434212ac6861070613eed3527e1a35358
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342472"
---
# <a name="how-to-change-service-accounts-and-passwords"></a>サービス アカウントおよびパスワードを変更する方法
BizTalk Server を構成した後で、組織のアカウント ポリシー (パスワード ポリシー、アカウント ロックアウト ポリシーなど) に従ってサービス アカウントまたはパスワードの変更を要求されるのが一般的です。 アカウント ポリシーの詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62172](http://go.microsoft.com/fwlink/?LinkId=62172)します。  
  
 サービス アカウントまたはパスワードを変更するには、次の手順を実行します。  
  
1. 新しいサービス アカウントを作成するか、既存のアカウントのパスワードを変更します。  
  
2. サービス アカウントが、必要な Windows グループのメンバーであることを確認します。 これには、サービス アカウントを追加する必要があります、ローカルまたはドメイン グループについては、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
   > [!NOTE]
   >  ドメイン グループ環境では、Active Directory ユーザーとコンピューター コンソールを使用します。 ローカル グループ環境では、コンピューターの管理コンソールを使用します。  
  
3. サービス アカウントの種類に応じて、次のタスクを行ってください。  
  
   |サービスまたはアカウント|ユーザー アカウントを変更する方法|ユーザー アカウントの変更後に必要なタスク|パスワードを変更する方法|パスワードの変更後に必要なタスク|  
   |------------------------|---------------------------------|-------------------------------------------------|-----------------------------|---------------------------------------------|  
   |マスター シークレット サーバーのエンタープライズ シングル サインオン サービス|1.マスター シークレットのバックアップが存在することを確認します。 詳細については、次を参照してください。[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)します。<br />2.サービス コンソールを使用してサービス アカウントを変更します。<br />3.マスター シークレットを復元します。 詳細については、次を参照してください。[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)します。|サービスを再起動します。|サービス コンソールを使用してアカウントのパスワードを変更します。|サービスを再起動します。|  
   |エンタープライズ シングル サインオン サービス|サービス コンソールを使用してサービス アカウントを変更します。|サービスを再起動します。|サービス コンソールを使用してアカウントのパスワードを変更します。|サービスを再起動します。|  
   |BizTalk ホスト インスタンス|BizTalk Server 管理コンソールを使用してサービス アカウントを変更します。|BizTalk ホスト インスタンスを再起動します。|BizTalk 管理コンソールまたはサービス コンソールを使用して、アカウントのパスワードを変更します。|BizTalk ホスト インスタンスを再起動します。|  
   |BizTalk 分離ホスト インスタンス、および SOAP 受信アダプターをホストしている対応するアプリケーション プール|1.BizTalk Server 管理コンソールを使用してサービス アカウントを変更します。<br />2.IIS 管理コンソールを使用して、アプリケーション プールのアカウントを変更**に注意してください。** アプリケーション プールのサービス アカウントは、対応する分離ホストのサービス アカウントに一致する必要があります。|1.IIS 管理コンソールを使用して、対応するアプリケーション プールのサービス アカウントを変更します。<br />2.IIS 管理コンソールを使用してアプリケーション プールを再起動します。|アプリケーション プールを実行するアカウントのパスワードを変更します。 IIS 管理コンソールを使用して**に注意してください。** パスワードを変更した後、BizTalk Server 管理コンソールでパスワードを変更する必要はありません。|1.IIS 管理コンソールを使用して、対応するアプリケーション プールの実行に使用するアカウントのパスワードを変更します。<br />2.IIS 管理コンソールを使用してアプリケーション プールを再起動します。|  
   |ルール エンジン更新サービス|構成マネージャー コンソールまたはサービス コンソールを使用してサービス アカウントを変更します。<br /><br /> 構成マネージャーは、自動的にサービスを再起動します。|サービス コンソールを使用する場合は、サービスを手動で再起動する必要があります。|構成マネージャー コンソールまたはサービス コンソールを使用してアカウントのパスワードを変更します。<br /><br /> 構成マネージャーは、自動的にサービスを再起動します。|サービス コンソールを使用する場合は、サービスを手動で再起動する必要があります。|  
   |BAM 通知サービス|1.BAM 通知サービスがインストールされた SQL サーバーに新しいアカウントを追加します。<br />2.新しいアカウントに特権を付与します。 必要な権限の詳細については、次を参照してください[Windows グループと BizTalk Server でのユーザー アカウント。](../core/windows-groups-and-user-accounts-in-biztalk-server.md)<br />3.サービス コンソールを使用してサービス アカウントを変更します。|サービスを再起動します。|サービス コンソールを使用してアカウントのパスワードを変更します。|サービスを再起動します。|  
   |BAM 管理 Web サービス|1.適切な SQL server に新しいアカウントを追加しでの権限を付与[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。<br />2.構成マネージャーを使用してユーザー アカウントを変更します。||構成マネージャーを使用してユーザー アカウントのパスワードを変更します。||  
   |BAM アプリケーション プール|Configuration Manager を使用して、アプリケーション プールのサービス アカウントを変更します。<br /><br /> 構成マネージャーは、自動的にアプリケーション プールを再利用します。||構成マネージャーを使用してアカウントのパスワードを変更します。<br /><br /> 構成マネージャーは、自動的にアプリケーション プールを再利用します。||  
  
   次の手順では、構成マネージャーを使用してサービス アカウントおよびパスワードを変更する方法について説明します。  
  
### <a name="to-change-service-accounts-and-passwords-using-configuration-manager"></a>構成マネージャーを使用してサービス アカウントおよびパスワードを変更するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。  
  
2. **Microsoft BizTalk Server 構成**、 をクリックして**ビュー**、 をクリックして**サービス アカウント**、し、サービス アカウントとパスワードを変更、 **サービス アカウント** ダイアログ ボックス。 構成マネージャーの詳細については、次を参照してください。[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)します。  
  
   > [!NOTE]
   >  構成マネージャーは、複数のコンピューターを管理するための中心的な場所ではありません。 Microsoft BizTalk Server を複数のコンピューター上にインストールする場合は、ランタイム コンピューターごとにサービス アカウントとパスワードを変更する必要があります。  
  
## <a name="see-also"></a>参照  
 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)   
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [ホストとサービス アカウントの管理](../core/managing-hosts-and-service-accounts.md)