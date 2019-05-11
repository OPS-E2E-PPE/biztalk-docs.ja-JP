---
title: 証明書ストアを復元する方法 |Microsoft Docs
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
ms.openlocfilehash: 22a31c1b1fb9c25050202aa4f5f69fcd39af424b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384099"
---
# <a name="how-to-restore-the-certificate-store"></a><span data-ttu-id="81366-102">証明書ストアを復元する方法</span><span class="sxs-lookup"><span data-stu-id="81366-102">How to Restore the Certificate Store</span></span>
<span data-ttu-id="81366-103">復旧処理の一環として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、証明書ストアを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81366-103">As a part of recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must restore the certificate store.</span></span> <span data-ttu-id="81366-104">回復する場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Standard Edition は、証明書ストアを復元するこの手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81366-104">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must use this procedure to restore the certificate store.</span></span> <span data-ttu-id="81366-105">その他のすべてのエディションを復旧する場合は、この手順を実行する必要はありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]回復プロセスは、証明書ストアを自動的に復元されるため、します。</span><span class="sxs-lookup"><span data-stu-id="81366-105">You do not need to perform this procedure when recovering all other editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] because the recovery process automatically restores the certificate store for you.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="81366-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="81366-106">Prerequisites</span></span>  
 <span data-ttu-id="81366-107">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81366-107">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a><span data-ttu-id="81366-108">証明書ストア (BizTalk Server の Standard Edition) を復元するには</span><span class="sxs-lookup"><span data-stu-id="81366-108">To restore the certificate store (BizTalk Server Standard Edition)</span></span>  
  
1.  <span data-ttu-id="81366-109">クリックして**開始**、 をクリックして**すべてのプログラム**、順にクリックします**Internet Explorer**します。</span><span class="sxs-lookup"><span data-stu-id="81366-109">Click **Start**, click **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="81366-110">**ツール** メニューのをクリックして**インターネット オプション**します。</span><span class="sxs-lookup"><span data-stu-id="81366-110">On the **Tools** menu, click **Internet Options**.</span></span>  
  
3.  <span data-ttu-id="81366-111">**インターネット オプション**ダイアログ ボックスで、をクリックして、**コンテンツ**タブをクリックし、をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="81366-111">In the **Internet Options** dialog box, click the **Content** tab, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="81366-112">**証明書**ダイアログ ボックスで、をクリックして、**その他のユーザー**タブをクリックし、をクリックし、**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="81366-112">In the **Certificates** dialog box, click the **Other People** tab, and then click **Import**.</span></span>  
  
5.  <span data-ttu-id="81366-113">**証明書のインポート ウィザード**、 をクリックして**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="81366-113">In the **Certificate Import Wizard**, click **Cancel**.</span></span>  
  
     <span data-ttu-id="81366-114">これを作成、 **AddressBook**レジストリ ハイブ。</span><span class="sxs-lookup"><span data-stu-id="81366-114">This creates the **AddressBook** hive in the registry.</span></span>  
  
6.  <span data-ttu-id="81366-115">**証明書**ダイアログ ボックスで、をクリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="81366-115">In the **Certificates** dialog box, click **Close**.</span></span>  
  
7.  <span data-ttu-id="81366-116">**インターネット オプション**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="81366-116">In the **Internet Options** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="81366-117">クリックして**ファイル**、順にクリックします**閉じる**を Internet Explorer を終了します。</span><span class="sxs-lookup"><span data-stu-id="81366-117">Click **File**, and then click **Close** to exit Internet Explorer.</span></span>  
  
9. <span data-ttu-id="81366-118">をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="81366-118">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="81366-119">レジストリ エディターでは、次のレジストリ キーに移動します。</span><span class="sxs-lookup"><span data-stu-id="81366-119">In Registry Editor, navigate to the following registry key:</span></span>  
  
     <span data-ttu-id="81366-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span><span class="sxs-lookup"><span data-stu-id="81366-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span></span>  
  
11. <span data-ttu-id="81366-121">いることを確認、 **AddressBook**ハイブが存在します。</span><span class="sxs-lookup"><span data-stu-id="81366-121">Verify that the **AddressBook** hive is present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81366-122">参照</span><span class="sxs-lookup"><span data-stu-id="81366-122">See Also</span></span>  
 [<span data-ttu-id="81366-123">BizTalk Server を実行しているコンピューターの復旧</span><span class="sxs-lookup"><span data-stu-id="81366-123">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)