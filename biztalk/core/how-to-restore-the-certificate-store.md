---
title: 証明書ストアを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c6f7551-d119-4668-9b52-6013f69a0302
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaeee6b762cf5af15ca7cba34864abd86682d4df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254698"
---
# <a name="how-to-restore-the-certificate-store"></a><span data-ttu-id="85e75-102">証明書ストアを復元する方法</span><span class="sxs-lookup"><span data-stu-id="85e75-102">How to Restore the Certificate Store</span></span>
<span data-ttu-id="85e75-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の復旧処理の一環として、証明書ストアを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e75-103">As a part of recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must restore the certificate store.</span></span> <span data-ttu-id="85e75-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition を復旧する場合は、この手順を使用して証明書ストアを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e75-104">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must use this procedure to restore the certificate store.</span></span> <span data-ttu-id="85e75-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の他のすべてのエディションを復旧する場合は、復旧処理によって自動的に証明書ストアが復元されるため、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="85e75-105">You do not need to perform this procedure when recovering all other editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] because the recovery process automatically restores the certificate store for you.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="85e75-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="85e75-106">Prerequisites</span></span>  
 <span data-ttu-id="85e75-107">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e75-107">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a><span data-ttu-id="85e75-108">証明書ストアを復元するには (BizTalk Server Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="85e75-108">To restore the certificate store (BizTalk Server Standard Edition)</span></span>  
  
1.  <span data-ttu-id="85e75-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、クリックして**Internet Explorer**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-109">Click **Start**, click **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="85e75-110">**ツール** メニューのをクリックして**インターネット オプション**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-110">On the **Tools** menu, click **Internet Options**.</span></span>  
  
3.  <span data-ttu-id="85e75-111">**インターネット オプション** ダイアログ ボックスをクリックして、**コンテンツ** タブをクリックして**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-111">In the **Internet Options** dialog box, click the **Content** tab, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="85e75-112">**証明書** ダイアログ ボックスをクリックして、**ほかの人** タブをクリックして**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-112">In the **Certificates** dialog box, click the **Other People** tab, and then click **Import**.</span></span>  
  
5.  <span data-ttu-id="85e75-113">**証明書のインポート ウィザード**をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-113">In the **Certificate Import Wizard**, click **Cancel**.</span></span>  
  
     <span data-ttu-id="85e75-114">これを作成、 **AddressBook**レジストリ ハイブです。</span><span class="sxs-lookup"><span data-stu-id="85e75-114">This creates the **AddressBook** hive in the registry.</span></span>  
  
6.  <span data-ttu-id="85e75-115">**証明書**ダイアログ ボックスで、をクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-115">In the **Certificates** dialog box, click **Close**.</span></span>  
  
7.  <span data-ttu-id="85e75-116">**インターネット オプション**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-116">In the **Internet Options** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="85e75-117">をクリックして**ファイル**、順にクリック**閉じる**を Internet Explorer を終了します。</span><span class="sxs-lookup"><span data-stu-id="85e75-117">Click **File**, and then click **Close** to exit Internet Explorer.</span></span>  
  
9. <span data-ttu-id="85e75-118">をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="85e75-118">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="85e75-119">レジストリ エディターで、次のレジストリ キーに移動します。</span><span class="sxs-lookup"><span data-stu-id="85e75-119">In Registry Editor, navigate to the following registry key:</span></span>  
  
     <span data-ttu-id="85e75-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span><span class="sxs-lookup"><span data-stu-id="85e75-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span></span>  
  
11. <span data-ttu-id="85e75-121">いることを確認、 **AddressBook**ハイブが存在します。</span><span class="sxs-lookup"><span data-stu-id="85e75-121">Verify that the **AddressBook** hive is present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e75-122">参照</span><span class="sxs-lookup"><span data-stu-id="85e75-122">See Also</span></span>  
 [<span data-ttu-id="85e75-123">BizTalk Server を実行しているコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="85e75-123">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)