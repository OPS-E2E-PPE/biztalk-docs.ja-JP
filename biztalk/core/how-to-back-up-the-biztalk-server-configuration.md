---
title: "BizTalk Server の構成をバックアップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad54aba8f8f49adeb8534bdbe28add15f0fe9638
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="2ac1e-102">BizTalk Server 構成をバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="2ac1e-102">How to Back Up The BizTalk Server Configuration</span></span>
<span data-ttu-id="2ac1e-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ処理の一環として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が実行されているコンピューターに関連付けられた構成設定をバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-103">As part of backing up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you should back up the configuration settings associated with the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2ac1e-104">元の構成ファイルのコピーを保持しておくと、コンピューターの交換が必要になるようなハードウェア障害が発生した場合の復元処理が大幅に簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-104">Having a copy of the original configuration file greatly simplifies the restoration process if you have a hardware failure that requires you to replace the computer.</span></span>  
  
 <span data-ttu-id="2ac1e-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が実行されている各コンピューターの構成設定は、BizTalk Server 構成マネージャーによって作成される XML ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-105">The configuration settings for each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are stored in an XML file created by the BizTalk Server Configuration Manager.</span></span> <span data-ttu-id="2ac1e-106">BizTalk Server の構成を変更するたびに、更新された構成ファイルをバックアップ先にエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-106">Any time you change the configuration of your BizTalk servers, you should export the updated configuration file to your backup location.</span></span> <span data-ttu-id="2ac1e-107">これにより、BizTalk Server を交換する必要がある場合に、構成ファイルを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-107">This helps to ensure that the configuration file is available if you have to replace your BizTalk server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ac1e-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="2ac1e-108">Prerequisites</span></span>  
 <span data-ttu-id="2ac1e-109">ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-109">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="2ac1e-110">BizTalk Server 構成をバックアップするには</span><span class="sxs-lookup"><span data-stu-id="2ac1e-110">To back up the BizTalk Server configuration</span></span>  
  
1.  <span data-ttu-id="2ac1e-111">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft BizTalk Server**、順にクリック**BizTalk Server 構成**です。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-111">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="2ac1e-112">**Microsoft BizTalk Server 構成**をクリックして**構成のエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-112">In **Microsoft BizTalk Server Configuration**, click **Export Configuration**.</span></span>  
  
3.  <span data-ttu-id="2ac1e-113">**名前を付けて保存**ダイアログ ボックスで、バックアップを格納する場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-113">In the **Save As** dialog box, browse to the location where you store your backups.</span></span>  
  
4.  <span data-ttu-id="2ac1e-114">**ファイル名**ボックスで、構成ファイルの名前を入力し、をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="2ac1e-114">In the **File name** box, type a name for the configuration file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac1e-115">参照</span><span class="sxs-lookup"><span data-stu-id="2ac1e-115">See Also</span></span>  
 <span data-ttu-id="2ac1e-116">[BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="2ac1e-116">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="2ac1e-117">BizTalk Server の構成を回復する方法</span><span class="sxs-lookup"><span data-stu-id="2ac1e-117">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)