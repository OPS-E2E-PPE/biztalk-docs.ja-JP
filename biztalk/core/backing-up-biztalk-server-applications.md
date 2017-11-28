---
title: "BizTalk Server アプリケーションのバックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b51e3ae6-08ed-48ca-8977-13f46144a5fa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d125a1430aa2d044abba7632fa31a9c89f2bc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-biztalk-server-applications"></a><span data-ttu-id="f43c9-102">BizTalk Server アプリケーションのバックアップ</span><span class="sxs-lookup"><span data-stu-id="f43c9-102">Backing Up BizTalk Server Applications</span></span>
<span data-ttu-id="f43c9-103">ハードウェア障害が発生した後、BizTalk Server システムを確実に復旧するには、適切なバックアップを作成しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="f43c9-103">To ensure that you can recover your BizTalk Server system after a hardware failure, it is important to have good backups.</span></span> <span data-ttu-id="f43c9-104">バックアップ計画では、BizTalk アプリケーションをリモート サーバーにエクスポートし、アプリケーションをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f43c9-104">As a part of keeping backups, it is a good idea to export your BizTalk applications to a remote server and to back up these applications.</span></span>  
  
 <span data-ttu-id="f43c9-105">こうしておくと、後で BizTalk Server データベースを復元して BizTalk Server を再インストールしたときに、バックアップしたアプリケーションをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="f43c9-105">Later, when you restore the BizTalk Server databases and reinstall BizTalk Server, you can import these applications.</span></span> <span data-ttu-id="f43c9-106">エクスポートして、アプリケーションをインポートする方法の詳細については、次を参照してください。[を管理する BizTalk アプリケーションの展開と](../core/deploying-and-managing-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="f43c9-106">For more information about how to export and import applications, see [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="f43c9-107">コンピュータに展開されているすべての BizTalk アプリケーションについて、.msi ファイルをエクスポートし、別のサーバー上のバックアップ場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="f43c9-107">For all BizTalk applications deployed on the computer, you should export the .msi files and save them in your backup location (on a different server).</span></span> <span data-ttu-id="f43c9-108">.msi ファイルを使用すると、コンピュータを復旧した後で BizTalk Server に必要なリソースを再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="f43c9-108">The .msi files enable you to reinstall the resources required by BizTalk Server after you recover the destination computer.</span></span> <span data-ttu-id="f43c9-109">.msi には必要なリソースをすべて含め、これらのリソースを .msi ファイルでインストールするときに必要な手順も指定しておきます。</span><span class="sxs-lookup"><span data-stu-id="f43c9-109">You should ensure that the .msi files include all of the required resources, and that you specify the actions to be performed on the .msi installation for these resources.</span></span> <span data-ttu-id="f43c9-110">BizTalk アプリケーションが、.msi ファイルに含まれていないユーザー アセンブリやその他の DLL に依存している場合は、これらのコンポーネントも別にバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43c9-110">If your BizTalk application depends on any user assemblies or other DLLs that are not included in the .msi files, you must back up them up separately.</span></span>  
  
 <span data-ttu-id="f43c9-111">アプリケーションのエクスポート手順は、コンテンツ ベースのルーティングやオーケストレーションが含まれる場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="f43c9-111">The application export process is the same for content-based routing scenarios as well as scenarios that have orchestrations.</span></span> <span data-ttu-id="f43c9-112">BizTalk アプリケーションを変更したときには、常にこの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43c9-112">You should repeat this process whenever you change the BizTalk applications.</span></span> <span data-ttu-id="f43c9-113">詳細については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="f43c9-113">For more information, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43c9-114">参照</span><span class="sxs-lookup"><span data-stu-id="f43c9-114">See Also</span></span>  
 [<span data-ttu-id="f43c9-115">BizTalk Server を実行しているコンピューターのバックアップ</span><span class="sxs-lookup"><span data-stu-id="f43c9-115">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)