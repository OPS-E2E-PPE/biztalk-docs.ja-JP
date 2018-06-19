---
title: ランタイム コンピューターを更新する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 576a7065-04b6-436c-acf9-28c8d6e40107
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca8edb4da6b59c33f87100ee3669bb2472d4350c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010899"
---
# <a name="how-to-update-the-runtime-computers"></a><span data-ttu-id="93389-102">ランタイム コンピューターを更新する方法</span><span class="sxs-lookup"><span data-stu-id="93389-102">How to Update the Runtime Computers</span></span>
<span data-ttu-id="93389-103">送信先システム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターで構成されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境で実行されている実稼働の BizTalk グループの一部として構成します。</span><span class="sxs-lookup"><span data-stu-id="93389-103">The destination system [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers are configured with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard as part of the production BizTalk group running in the production environment.</span></span> <span data-ttu-id="93389-104">各設定を更新する必要があります、障害回復環境で実稼働の BizTalk グループが復元される場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ことは、災害復旧を指すように、ランタイム コンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]復元されたに接続しようとしたときのインスタンス運用環境の BizTalk グループです。</span><span class="sxs-lookup"><span data-stu-id="93389-104">When the production BizTalk group is restored in the disaster recovery environment, settings must be updated on each [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computer so that it points to the disaster recovery [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s) when it attempts to connect to the restored production BizTalk group.</span></span> <span data-ttu-id="93389-105">送信先システムに、BizTalk グループが復元されると後、に、次の手順を使用して更新、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。</span><span class="sxs-lookup"><span data-stu-id="93389-105">After the BizTalk group is restored in the destination system, use the following procedure to update the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers.</span></span>  
  
### <a name="to-update-the-biztalk-server-runtime-computers"></a><span data-ttu-id="93389-106">BizTalk Server ランタイム コンピューターを更新するには</span><span class="sxs-lookup"><span data-stu-id="93389-106">To update the BizTalk Server runtime computers</span></span>  
  
1.  <span data-ttu-id="93389-107">\Program Files\Microsoft すべて 32 ビット BizTalk server 上の BizTalk Server\Schema\Restore ディレクトリまたはすべての 64 ビット BizTalk で: \Program Files (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore ディレクトリには、編集した SampleUpdateInfo.xml ファイルをコピーします。送信先システム内のサーバー。</span><span class="sxs-lookup"><span data-stu-id="93389-107">Copy the edited SampleUpdateInfo.xml file to the \Program Files\Microsoft BizTalk Server\Schema\Restore directory on every 32 bit BizTalk server or to the \Program Files (x86)\Microsoft BizTalk Server\Bins32\Schema\Restore directory on every 64 bit BizTalk server in the destination system.</span></span>  
  
2.  <span data-ttu-id="93389-108">各 BizTalk server では、コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="93389-108">On each BizTalk server, open a command prompt.</span></span> <span data-ttu-id="93389-109">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="93389-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93389-110">64 ビット コンピューターでは、64 ビット コマンド プロンプトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="93389-110">On 64-bit computers, you must open a 64-bit command prompt.</span></span>  
  
3.  <span data-ttu-id="93389-111">コマンド プロンプトで、または (64 ビット コンピューター) 上の \Program Files (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore \Program Files\Microsoft BizTalk Server\Schema\Restore (32 ビット コンピューター) 上に移動し、このコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="93389-111">At the command-prompt, navigate to \Program Files\Microsoft BizTalk Server\Schema\Restore (on 32 bit computers) or to \Program Files (x86)\Microsoft BizTalk Server\Bins32\Schema\Restore (on 64 bit computers) and type this command:</span></span>  
  
    ```  
    cscript UpdateRegistry.vbs SampleUpdateInfo.xml  
    ```  
  
4.  <span data-ttu-id="93389-112">有効にし、送信先システムにすべての BizTalk ホスト インスタンスおよび BizTalk server 上の他のすべての BizTalk サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="93389-112">Enable and restart all BizTalk Host instances and all other BizTalk Services on the BizTalk servers in the destination system.</span></span>  
  
5.  <span data-ttu-id="93389-113">送信先システムで、各 BizTalk サーバーで WMI を再起動します。</span><span class="sxs-lookup"><span data-stu-id="93389-113">Restart WMI on each BizTalk server in the destination system.</span></span> <span data-ttu-id="93389-114">をクリックして**開始**、 をクリックして**実行**、型**services.msc**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="93389-114">Click **Start**, click **Run**, type **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="93389-115">**Services** MMC スナップインで、右クリックして**Windows Management Instrumentation**を選択し、**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="93389-115">In the **Services** MMC snap-in, right-click **Windows Management Instrumentation** and select **Restart**.</span></span>  
  
6.  <span data-ttu-id="93389-116">各 BizTalk サーバーで開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**BizTalk グループ**、し、**削除**です。</span><span class="sxs-lookup"><span data-stu-id="93389-116">On each BizTalk server, open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **BizTalk Group**, and then select **Remove**.</span></span>  
  
7.  <span data-ttu-id="93389-117">右クリック**BizTalk Server 2010 管理**[**既存グループに接続**SQL Server データベース インスタンスを選択して、データベースの名前の BizTalk 管理データベースに対応します。クリックして BizTalk グループ]、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="93389-117">Right-click **BizTalk Server 2010 Administration**, select **Connect to Existing Group**, select the SQL Server database instance and database name that corresponds to the BizTalk Management database for the BizTalk group, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93389-118">更新した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターでは、する必要がありますも更新、 **SSO サーバー名**に表示されるとおり、**グループのプロパティ** ダイアログ ボックスで使用できる、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="93389-118">After updating the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime computers, you may also need to update the **SSO Server name** as displayed in the **Group Properties** dialog box available in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="93389-119">更新する、 **SSO サーバー名**、起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理 を右クリックし、 **BizTalk グループ**ノードと選択**プロパティ**を表示する、**全般**のタブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="93389-119">To update the **SSO Server name**, launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click to expand [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration, right-click the **BizTalk Group** node and select **Properties** to display the **General** tab of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="93389-120">その後、、 **SSO サーバー名** ボックスに、アダプターの構成情報にアクセスして このコンピューターが使用するエンタープライズ シングル サインオン サーバーの名前を入力**OK**です。</span><span class="sxs-lookup"><span data-stu-id="93389-120">Then, in the **SSO Server name** textbox, enter the name of the Enterprise Single Sign-On server that this computer will use to access the configuration information for the adapters and click **OK**.</span></span> <span data-ttu-id="93389-121">これは、SSO データベースへの接続に使用する SSO サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="93389-121">This is the name of the SSO server used to connect to the SSO database.</span></span>  
  
8.  <span data-ttu-id="93389-122">各 BizTalk ランタイム サーバーで次の Windows サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="93389-122">Restart the following Windows services on each BizTalk runtime server:</span></span>  
  
    -   <span data-ttu-id="93389-123">エンタープライズ SSO サービス</span><span class="sxs-lookup"><span data-stu-id="93389-123">Enterprise SSO Service</span></span>  
  
    -   <span data-ttu-id="93389-124">ルール エンジン更新サービス</span><span class="sxs-lookup"><span data-stu-id="93389-124">Rule Engine Update Service</span></span>  
  
    -   <span data-ttu-id="93389-125">BizTalk ホスト インスタンス</span><span class="sxs-lookup"><span data-stu-id="93389-125">BizTalk Host Instances</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93389-126">参照</span><span class="sxs-lookup"><span data-stu-id="93389-126">See Also</span></span>  
 [<span data-ttu-id="93389-127">ランタイム コンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="93389-127">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)