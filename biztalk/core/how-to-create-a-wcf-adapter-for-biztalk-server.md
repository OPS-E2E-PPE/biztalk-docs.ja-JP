---
title: "BizTalk Server の WCF アダプターを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ddaeb72-d263-4291-bd79-485fc736e6e7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe1bbb9282db88f1b4370cea4b59ff4fcbfe6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-wcf-adapter-for-biztalk-server"></a><span data-ttu-id="f7071-102">BizTalk Server の WCF アダプタを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f7071-102">How to Create a WCF Adapter for BizTalk Server</span></span>
<span data-ttu-id="f7071-103">BizTalk [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] アダプタの作成作業は、3 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f7071-103">There are three parts to creating a BizTalk [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] adapter.</span></span>  
  
-   <span data-ttu-id="f7071-104">BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービス公開ウィザードを使用して、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7071-104">Create a [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web service using the BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Publishing Wizard.</span></span> <span data-ttu-id="f7071-105">BizTalk の使用方法について[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービス公開ウィザードを参照してください[WCF サービスの公開](../core/publishing-wcf-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7071-105">For information about using the BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Publishing Wizard, see [Publishing WCF Services](../core/publishing-wcf-services.md).</span></span>  
  
-   <span data-ttu-id="f7071-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信と送信の場所およびポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7071-106">Configure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive and send locations and ports by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f7071-107">これを行う方法の例は、次を参照してください。[方法の構成を受信および送信場所とポートを BAM WCF インターセプション用](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7071-107">For an example of how to do this, see [How to Configure Receive and Send Locations and Ports for BAM WCF Interception](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md).</span></span>  
  
-   <span data-ttu-id="f7071-108">ソリューションを IIS でホストしている場合は、IIS マネージャーを使用して、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web サービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7071-108">If you are hosting your solution in IIS, you must configure the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web service by using IIS Manager.</span></span>  
  
    -   <span data-ttu-id="f7071-109">アプリケーション プール ユーザーにアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7071-109">You must grant permissions to the App pool user.</span></span> <span data-ttu-id="f7071-110">これを行うには、次を参照してください。 [IIS の偽装のセキュリティに関する考慮事項](../core/security-considerations-for-iis-impersonation.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7071-110">To do this, see [Security Considerations for IIS Impersonation](../core/security-considerations-for-iis-impersonation.md).</span></span>  
  
    -   <span data-ttu-id="f7071-111">次の手順に従って、アプリケーションのディレクトリ セキュリティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7071-111">You must set the directory security for your application as described in the following procedure.</span></span>  
  
## <a name="setting-the-directory-security"></a><span data-ttu-id="f7071-112">ディレクトリ セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="f7071-112">Setting the Directory Security</span></span>  
 <span data-ttu-id="f7071-113">[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サービスのディレクトリ セキュリティのアクセス制御で、匿名アクセスが許可されていることを確認します。これにより、アプリケーションへのアクセスが容易になります。</span><span class="sxs-lookup"><span data-stu-id="f7071-113">Ensure that the Directory Security Access Control for the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service allows for anonymous access; this simplifies the application access.</span></span>  
  
 <span data-ttu-id="f7071-114">たとえば、アプリケーションの名前が MyBizTalkService3 が既定の web サイトを MyBizTalkService3 がある場合は、アクセス制御を設定するには、この手順は次です。</span><span class="sxs-lookup"><span data-stu-id="f7071-114">For example, if your application is named MyBizTalkService3 and you have a MyBizTalkService3 that is in Default Websites, you would follow this procedure to set the access control.</span></span>  
  
#### <a name="to-set-the-access-control-in-windows-server-2008"></a><span data-ttu-id="f7071-115">Windows Server 2008 でアクセス制御を設定するには</span><span class="sxs-lookup"><span data-stu-id="f7071-115">To set the access control in Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="f7071-116">をクリックして**開始**、 をクリックして**すべてのプログラム**、展開**管理ツール**をクリックし、**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="f7071-116">Click **Start**, click **All Programs**, expand **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="f7071-117">インターネット インフォメーション サービス (IIS) マネージャー ウィンドウで、サーバー名を展開し、**サイト**、展開**インターネット インフォメーション サービス**、順に展開**Default Web Site**.</span><span class="sxs-lookup"><span data-stu-id="f7071-117">In the Internet Information Services (IIS) Manager window, expand your server name, expand **Sites**, expand **Internet Information Services**, and then expand **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="f7071-118">右クリック**MyBizTalkService3**、クリックして**アクセス許可の編集**です。</span><span class="sxs-lookup"><span data-stu-id="f7071-118">Right-click **MyBizTalkService3**, and then click **Edit Permissions**.</span></span>  
  
4.  <span data-ttu-id="f7071-119">**セキュリティ**のタブ、 **MyBizTalkService3 のプロパティ**ダイアログ ボックスで、をクリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="f7071-119">On the **Security** tab of the **MyBizTalkService3 Properties** dialog box, click **Edit**.</span></span>  
  
5.  <span data-ttu-id="f7071-120">**MyBizTalkService3 のアクセス許可**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="f7071-120">In the **Permissions for MyBizTalkService3** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="f7071-121">**ユーザー、コンピューター、またはグループ** ダイアログ ボックスで、「 `anonymous logon`  をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="f7071-121">In the **Select Users, Computers, or Groups** dialog box, type `anonymous logon` and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="f7071-122">選択**ANONYMOUS LOGON**で、**グループまたはユーザー名**セクションで、**読み取り & 実行**で、 **ANONYMOUS LOGON のアクセス許可**セクションで、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f7071-122">Select **ANONYMOUS LOGON** in the **Group or user names** section, select **Read & execute** in the **Permissions for ANONYMOUS LOGON** section, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="f7071-123">をクリックして**OK**を閉じる、 **MyBizTalkService3 のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f7071-123">Click **OK** to close the **MyBizTalkService3 Properties** dialog box.</span></span>  
  
 <span data-ttu-id="f7071-124">サービスが正しく構成されていることを確認する、サービスを右クリックし、をクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="f7071-124">To confirm that the service is configured correctly, right-click the service, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="f7071-125">サービスが適切に構成されている場合は、次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7071-125">If the service is configured correctly, you will see a screen similar to the one below.</span></span>  
  
 <span data-ttu-id="f7071-126">![BizTalkServiceInstance サービス画面](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")</span><span class="sxs-lookup"><span data-stu-id="f7071-126">![BizTalkServiceInstance Service Screen](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7071-127">参照</span><span class="sxs-lookup"><span data-stu-id="f7071-127">See Also</span></span>  
 [<span data-ttu-id="f7071-128">BAM データを受信する WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="f7071-128">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)