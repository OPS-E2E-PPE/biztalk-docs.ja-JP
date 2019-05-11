---
title: BizTalk Server の構成をバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da0d382752a7f3469a8f10a3f2550b06fe84bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342654"
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="d9630-102">BizTalk Server の構成をバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="d9630-102">How to Back Up The BizTalk Server Configuration</span></span>
<span data-ttu-id="d9630-103">バックアップ処理の一環として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、実行しているコンピューターに関連付けられている構成設定をバックアップする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d9630-103">As part of backing up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you should back up the configuration settings associated with the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d9630-104">コンピューターを交換する必要があるハードウェア障害がある場合、元の構成ファイルのコピーを大幅にも、復元プロセスが簡略化します。</span><span class="sxs-lookup"><span data-stu-id="d9630-104">Having a copy of the original configuration file greatly simplifies the restoration process if you have a hardware failure that requires you to replace the computer.</span></span>  
  
 <span data-ttu-id="d9630-105">実行する各コンピューターの構成設定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk Server 構成マネージャーで作成された XML ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d9630-105">The configuration settings for each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are stored in an XML file created by the BizTalk Server Configuration Manager.</span></span> <span data-ttu-id="d9630-106">いつでも、BizTalk server の構成を変更するバックアップの場所に更新された構成ファイルをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9630-106">Any time you change the configuration of your BizTalk servers, you should export the updated configuration file to your backup location.</span></span> <span data-ttu-id="d9630-107">これにより、構成ファイルが、BizTalk server を交換する必要がある場合に使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9630-107">This helps to ensure that the configuration file is available if you have to replace your BizTalk server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d9630-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="d9630-108">Prerequisites</span></span>  
 <span data-ttu-id="d9630-109">この手順を実行する BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9630-109">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="d9630-110">BizTalk Server 構成をバックアップするには</span><span class="sxs-lookup"><span data-stu-id="d9630-110">To back up the BizTalk Server configuration</span></span>  
  
1.  <span data-ttu-id="d9630-111">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 構成**します。</span><span class="sxs-lookup"><span data-stu-id="d9630-111">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="d9630-112">**Microsoft BizTalk Server 構成**、 をクリックして**構成のエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="d9630-112">In **Microsoft BizTalk Server Configuration**, click **Export Configuration**.</span></span>  
  
3.  <span data-ttu-id="d9630-113">**付けて** ダイアログ ボックスで、バックアップを保存する場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="d9630-113">In the **Save As** dialog box, browse to the location where you store your backups.</span></span>  
  
4.  <span data-ttu-id="d9630-114">**ファイル名**ボックスで、構成ファイルの名前を入力し、クリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="d9630-114">In the **File name** box, type a name for the configuration file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9630-115">参照</span><span class="sxs-lookup"><span data-stu-id="d9630-115">See Also</span></span>  
 <span data-ttu-id="d9630-116">[BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="d9630-116">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="d9630-117">BizTalk Server の構成を回復する方法</span><span class="sxs-lookup"><span data-stu-id="d9630-117">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)