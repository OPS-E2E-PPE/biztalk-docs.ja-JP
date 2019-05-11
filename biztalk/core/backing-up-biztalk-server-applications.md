---
title: BizTalk Server アプリケーションのバックアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b51e3ae6-08ed-48ca-8977-13f46144a5fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5f209ea114cb515e0d09f5ddd80bbf864501038
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530613"
---
# <a name="backing-up-biztalk-server-applications"></a><span data-ttu-id="17cfb-102">BizTalk Server アプリケーションのバックアップ</span><span class="sxs-lookup"><span data-stu-id="17cfb-102">Backing Up BizTalk Server Applications</span></span>
<span data-ttu-id="17cfb-103">ハードウェア障害の後、BizTalk Server システムを回復できることを確認するには、適切なバックアップがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="17cfb-103">To ensure that you can recover your BizTalk Server system after a hardware failure, it is important to have good backups.</span></span> <span data-ttu-id="17cfb-104">、ままの状態のバックアップの一部としては、BizTalk アプリケーションをリモート サーバーをエクスポートして、これらのアプリケーションをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="17cfb-104">As a part of keeping backups, it is a good idea to export your BizTalk applications to a remote server and to back up these applications.</span></span>  
  
 <span data-ttu-id="17cfb-105">後で、BizTalk Server データベースを復元して、BizTalk Server を再インストールするときに、これらのアプリケーションをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="17cfb-105">Later, when you restore the BizTalk Server databases and reinstall BizTalk Server, you can import these applications.</span></span> <span data-ttu-id="17cfb-106">エクスポートして、アプリケーションをインポートする方法の詳細については、次を参照してください。 [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="17cfb-106">For more information about how to export and import applications, see [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="17cfb-107">コンピューターに展開されているすべての BizTalk アプリケーションを .msi ファイルをエクスポートして (別のサーバー) 上のバックアップ場所に保存をします。</span><span class="sxs-lookup"><span data-stu-id="17cfb-107">For all BizTalk applications deployed on the computer, you should export the .msi files and save them in your backup location (on a different server).</span></span> <span data-ttu-id="17cfb-108">.Msi ファイルを使用すると、セットアップ先のコンピューターを回復した後に、BizTalk Server で必要なリソースを再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="17cfb-108">The .msi files enable you to reinstall the resources required by BizTalk Server after you recover the destination computer.</span></span> <span data-ttu-id="17cfb-109">.Msi ファイルに、必要なリソースが含まれていると、これらのリソースの .msi のインストールで実行するアクションを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="17cfb-109">You should ensure that the .msi files include all of the required resources, and that you specify the actions to be performed on the .msi installation for these resources.</span></span> <span data-ttu-id="17cfb-110">場合は、BizTalk アプリケーションは、すべてのユーザー アセンブリまたは .msi ファイルに含まれていないその他の Dll に依存する必要がありますをバックアップすることを個別にします。</span><span class="sxs-lookup"><span data-stu-id="17cfb-110">If your BizTalk application depends on any user assemblies or other DLLs that are not included in the .msi files, you must back up them up separately.</span></span>  
  
 <span data-ttu-id="17cfb-111">アプリケーションのエクスポート手順は、オーケストレーションのシナリオと、コンテンツ ベース ルーティングのシナリオと同じです。</span><span class="sxs-lookup"><span data-stu-id="17cfb-111">The application export process is the same for content-based routing scenarios as well as scenarios that have orchestrations.</span></span> <span data-ttu-id="17cfb-112">BizTalk アプリケーションを変更するたびに、このプロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="17cfb-112">You should repeat this process whenever you change the BizTalk applications.</span></span> <span data-ttu-id="17cfb-113">詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="17cfb-113">For more information, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17cfb-114">参照</span><span class="sxs-lookup"><span data-stu-id="17cfb-114">See Also</span></span>  
 [<span data-ttu-id="17cfb-115">BizTalk Server を実行しているコンピューターのバックアップ</span><span class="sxs-lookup"><span data-stu-id="17cfb-115">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)