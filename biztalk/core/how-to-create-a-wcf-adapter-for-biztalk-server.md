---
title: BizTalk Server の WCF アダプターを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ddaeb72-d263-4291-bd79-485fc736e6e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe1bbb9282db88f1b4370cea4b59ff4fcbfe6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249346"
---
# <a name="how-to-create-a-wcf-adapter-for-biztalk-server"></a>BizTalk Server の WCF アダプタを作成する方法
BizTalk [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] アダプタの作成作業は、3 つの部分で構成されます。  
  
-   BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービス公開ウィザードを使用して、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web サービスを作成します。 BizTalk の使用方法について[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス公開ウィザードを参照してください[WCF サービスの公開](../core/publishing-wcf-services.md)です。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信と送信の場所およびポートを構成します。 これを行う方法の例は、次を参照してください。[方法の構成を受信および送信場所とポートを BAM WCF インターセプション用](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)です。  
  
-   ソリューションを IIS でホストしている場合は、IIS マネージャーを使用して、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web サービスを構成する必要があります。  
  
    -   アプリケーション プール ユーザーにアクセス許可を付与する必要があります。 これを行うには、次を参照してください。 [IIS の偽装のセキュリティに関する考慮事項](../core/security-considerations-for-iis-impersonation.md)です。  
  
    -   次の手順に従って、アプリケーションのディレクトリ セキュリティを設定する必要があります。  
  
## <a name="setting-the-directory-security"></a>ディレクトリ セキュリティの設定  
 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのディレクトリ セキュリティのアクセス制御で、匿名アクセスが許可されていることを確認します。これにより、アプリケーションへのアクセスが容易になります。  
  
 たとえば、アプリケーションの名前が MyBizTalkService3 が既定の web サイトを MyBizTalkService3 がある場合は、アクセス制御を設定するには、この手順は次です。  
  
#### <a name="to-set-the-access-control-in-windows-server-2008"></a>Windows Server 2008 でアクセス制御を設定するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、展開**管理ツール**をクリックし、**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  インターネット インフォメーション サービス (IIS) マネージャー ウィンドウで、サーバー名を展開し、**サイト**、展開**インターネット インフォメーション サービス**、順に展開**Default Web Site**.  
  
3.  右クリック**MyBizTalkService3**、クリックして**アクセス許可の編集**です。  
  
4.  **セキュリティ**のタブ、 **MyBizTalkService3 のプロパティ**ダイアログ ボックスで、をクリックして**編集**です。  
  
5.  **MyBizTalkService3 のアクセス許可**ダイアログ ボックスで、をクリックして**追加**です。  
  
6.  **ユーザー、コンピューター、またはグループ** ダイアログ ボックスで、「 `anonymous logon`  をクリックし、 **OK**です。  
  
7.  選択**ANONYMOUS LOGON**で、**グループまたはユーザー名**セクションで、**読み取り & 実行**で、 **ANONYMOUS LOGON のアクセス許可**セクションで、クリックして**OK**です。  
  
8.  をクリックして**OK**を閉じる、 **MyBizTalkService3 のプロパティ** ダイアログ ボックス。  
  
 サービスが正しく構成されていることを確認する、サービスを右クリックし、をクリックして**参照**です。  
  
 サービスが適切に構成されている場合は、次のような画面が表示されます。  
  
 ![BizTalkServiceInstance サービス画面](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")  
  
## <a name="see-also"></a>参照  
 [BAM データを受信する WCF アダプタの構成](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)