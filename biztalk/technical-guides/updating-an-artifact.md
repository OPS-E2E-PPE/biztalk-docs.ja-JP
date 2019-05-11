---
title: アイテムの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40feab57-4286-4bdf-8f52-25d02b3fa60c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4744fa7181e1ee290357f0a694e326e2ac22e1f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261413"
---
# <a name="updating-an-artifact"></a><span data-ttu-id="4879b-102">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="4879b-102">Updating an Artifact</span></span>
<span data-ttu-id="4879b-103">2 つ以上の BizTalk アプリケーションにおけるアイテム間の依存関係には、アプリケーションの展開と保守に大きな影響を及ぼすことができます。</span><span class="sxs-lookup"><span data-stu-id="4879b-103">Dependencies between artifacts in two or more BizTalk applications can have a significant effect on application deployment and maintenance.</span></span> <span data-ttu-id="4879b-104">成果物は、その成果物を適切に機能するために使用する必要があるとき、依存関係をたとえば、オーケストレーションが必要なメッセージを正しく送信するために特定のパイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="4879b-104">An artifact is dependent on another when it needs to use that artifact in order to function properly, for example an orchestration that needs to use a specific pipeline in order to transmit messages correctly.</span></span>  
  
 <span data-ttu-id="4879b-105">アプリケーションのアイテムを更新するには、必要があります最初を展開解除する、それに依存するすべてのアーティファクトと共にします。</span><span class="sxs-lookup"><span data-stu-id="4879b-105">To update an artifact in an application, you must first undeploy it, along with any artifacts that depend on it.</span></span> <span data-ttu-id="4879b-106">依存関係のある成果物は、同じアプリケーションに存在するときに BizTalk Server は自動的に更新され、依存アイテムの展開解除と再展開のタスクを処理します。</span><span class="sxs-lookup"><span data-stu-id="4879b-106">When artifacts that have dependencies exist in the same application, BizTalk Server automatically handles the undeployment and redeployment tasks for the updated and dependent artifacts.</span></span> <span data-ttu-id="4879b-107">依存関係のある成果物は、さまざまなアプリケーションに存在するときにただし、これは、当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="4879b-107">When artifacts that have dependencies exist in different applications, however, this is not the case.</span></span> <span data-ttu-id="4879b-108">場合は 1 つのアプリケーション内のアイテムを更新して、それに依存している別のアプリケーション内のアイテム、解除して、依存するアイテムを次のように手動で再デプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4879b-108">If you want to update an artifact in one application, and an artifact in another application has a dependency on it, you must undeploy and redeploy the dependent artifact manually as follows:</span></span>  
  
1. <span data-ttu-id="4879b-109">停止、参加解除、および依存するアイテムをバインド解除します。</span><span class="sxs-lookup"><span data-stu-id="4879b-109">Stop, unenlist, and unbind the dependent artifact.</span></span>  
  
2. <span data-ttu-id="4879b-110">依存するアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="4879b-110">Update the artifact on which it depends.</span></span>  
  
3. <span data-ttu-id="4879b-111">バインドし、参加、依存するアイテムを開始します。</span><span class="sxs-lookup"><span data-stu-id="4879b-111">Bind, enlist, and start the dependent artifact.</span></span>  
  
   <span data-ttu-id="4879b-112">手動でアイテムを更新する手順を実行する必要を回避するために他の成果物が依存して、同じアプリケーションの依存関係を持つすべての成果物をまとめておくために利用できます。</span><span class="sxs-lookup"><span data-stu-id="4879b-112">To avoid the need to perform manual steps to update an artifact on which other artifacts depend, you can try to keep all artifacts with dependencies together in the same application.</span></span> <span data-ttu-id="4879b-113">これは常に可能であれば、ただし、ほとんどの種類のアイテムを BizTalk グループ内で一意でなければならないためです。</span><span class="sxs-lookup"><span data-stu-id="4879b-113">This is not always possible, however, because most types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="4879b-114">両方のアプリケーションが同じアイテムに依存するアイテムが含まれている場合でも、同じグループに 2 つのアプリケーションで同じ成果物ことはできません。</span><span class="sxs-lookup"><span data-stu-id="4879b-114">You cannot have the same artifact in two different applications in the same group, even if both applications contain artifacts that depend on the same artifact.</span></span> <span data-ttu-id="4879b-115">一意の成果物の問題に関する詳細については、次を参照してください。[成果物をする必要がありますする内で一意で、アプリケーションまたはグループ](http://go.microsoft.com/fwlink/?LinkId=155141)(<http://go.microsoft.com/fwlink/?LinkId=155141>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="4879b-115">For more information about the issue of unique artifacts, see [Artifacts That Must Be Unique in an Application or Group](http://go.microsoft.com/fwlink/?LinkId=155141) (<http://go.microsoft.com/fwlink/?LinkId=155141>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
   <span data-ttu-id="4879b-116">1 つのアプリケーションに必要なアイテムを追加し、それに依存するアイテムを含むその他のアプリケーションからそのアプリケーションへの参照を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4879b-116">You can add the needed artifact to one application and then add a reference to that application from any other applications containing artifacts that depend on it.</span></span> <span data-ttu-id="4879b-117">アプリケーションへの参照を追加すると、アプリケーションのアイテムは、それが参照するアプリケーションですべてのアイテムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4879b-117">When you add a reference to an application, artifacts in the application can use any artifacts in the application that it references.</span></span> <span data-ttu-id="4879b-118">参照を追加する方法の詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](http://go.microsoft.com/fwlink/?LinkID=155011)(<http://go.microsoft.com/fwlink/?LinkID=155011>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="4879b-118">For instructions on adding a reference, see [How to Add a Reference to Another Application](http://go.microsoft.com/fwlink/?LinkID=155011) (<http://go.microsoft.com/fwlink/?LinkID=155011>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
   <span data-ttu-id="4879b-119">BizTalk アプリケーション内のアイテムを更新するためのタスクのチェックリストについては、次を参照してください。[チェックリスト。BizTalk アプリケーション内のアイテムの更新](http://go.microsoft.com/fwlink/?LinkId=155647)(<http://go.microsoft.com/fwlink/?LinkId=155647>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="4879b-119">For a checklist of tasks for updating artifacts in a BizTalk application, see [Checklist: Update the Artifacts in a BizTalk Application](http://go.microsoft.com/fwlink/?LinkId=155647) (<http://go.microsoft.com/fwlink/?LinkId=155647>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4879b-120">参照</span><span class="sxs-lookup"><span data-stu-id="4879b-120">See Also</span></span>  
 [<span data-ttu-id="4879b-121">アプリケーションとアイテムの更新</span><span class="sxs-lookup"><span data-stu-id="4879b-121">Updating Applications and Artifacts</span></span>](../technical-guides/updating-applications-and-artifacts.md)