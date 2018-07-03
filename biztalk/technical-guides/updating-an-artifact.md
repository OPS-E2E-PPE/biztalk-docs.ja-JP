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
ms.openlocfilehash: f32efa6195013d77ee368c0678a9ca67afb4e6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980043"
---
# <a name="updating-an-artifact"></a><span data-ttu-id="c6ac5-102">アイテムの更新</span><span class="sxs-lookup"><span data-stu-id="c6ac5-102">Updating an Artifact</span></span>
<span data-ttu-id="c6ac5-103">2 つ以上の BizTalk アプリケーションにおけるアイテム間の依存関係には、アプリケーションの展開と保守に大きな影響を及ぼすことができます。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-103">Dependencies between artifacts in two or more BizTalk applications can have a significant effect on application deployment and maintenance.</span></span> <span data-ttu-id="c6ac5-104">成果物は、その成果物を適切に機能するために使用する必要があるとき、依存関係をたとえば、オーケストレーションが必要なメッセージを正しく送信するために特定のパイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-104">An artifact is dependent on another when it needs to use that artifact in order to function properly, for example an orchestration that needs to use a specific pipeline in order to transmit messages correctly.</span></span>  
  
 <span data-ttu-id="c6ac5-105">アプリケーションのアイテムを更新するには、必要があります最初を展開解除する、それに依存するすべてのアーティファクトと共にします。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-105">To update an artifact in an application, you must first undeploy it, along with any artifacts that depend on it.</span></span> <span data-ttu-id="c6ac5-106">依存関係にあるアイテムが同じアプリケーション内に存在する場合、更新されるアイテムと依存するアイテムの展開解除タスクと再展開タスクが、BizTalk Server によって自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-106">When artifacts that have dependencies exist in the same application, BizTalk Server automatically handles the undeployment and redeployment tasks for the updated and dependent artifacts.</span></span> <span data-ttu-id="c6ac5-107">しかし、依存関係にあるアイテムが別のアプリケーションに存在する場合は、動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-107">When artifacts that have dependencies exist in different applications, however, this is not the case.</span></span> <span data-ttu-id="c6ac5-108">場合は 1 つのアプリケーション内のアイテムを更新して、それに依存している別のアプリケーション内のアイテム、解除して、依存するアイテムを次のように手動で再デプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-108">If you want to update an artifact in one application, and an artifact in another application has a dependency on it, you must undeploy and redeploy the dependent artifact manually as follows:</span></span>  
  
1. <span data-ttu-id="c6ac5-109">依存するアイテムの停止、参加解除、およびバインド解除を行います。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-109">Stop, unenlist, and unbind the dependent artifact.</span></span>  
  
2. <span data-ttu-id="c6ac5-110">依存先のアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-110">Update the artifact on which it depends.</span></span>  
  
3. <span data-ttu-id="c6ac5-111">依存するアイテムをバインドし、参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-111">Bind, enlist, and start the dependent artifact.</span></span>  
  
   <span data-ttu-id="c6ac5-112">手動でアイテムを更新する手順を実行する必要を回避するために他の成果物が依存して、同じアプリケーションの依存関係を持つすべての成果物をまとめておくために利用できます。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-112">To avoid the need to perform manual steps to update an artifact on which other artifacts depend, you can try to keep all artifacts with dependencies together in the same application.</span></span> <span data-ttu-id="c6ac5-113">これは常に可能であれば、ただし、ほとんどの種類のアイテムを BizTalk グループ内で一意でなければならないためです。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-113">This is not always possible, however, because most types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="c6ac5-114">同じグループ内の 2 つの異なるアプリケーションに、同一アイテムに依存するアイテムが含まれていても、その同一アイテムを両方のアプリケーション内に含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-114">You cannot have the same artifact in two different applications in the same group, even if both applications contain artifacts that depend on the same artifact.</span></span> <span data-ttu-id="c6ac5-115">一意の成果物の問題に関する詳細については、次を参照してください。[成果物をする必要がありますする内で一意で、アプリケーションまたはグループ](http://go.microsoft.com/fwlink/?LinkId=155141)(<http://go.microsoft.com/fwlink/?LinkId=155141>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-115">For more information about the issue of unique artifacts, see [Artifacts That Must Be Unique in an Application or Group](http://go.microsoft.com/fwlink/?LinkId=155141) (<http://go.microsoft.com/fwlink/?LinkId=155141>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
   <span data-ttu-id="c6ac5-116">1 つのアプリケーションに必要なアイテムを追加し、それに依存するアイテムを含むその他のアプリケーションからそのアプリケーションへの参照を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-116">You can add the needed artifact to one application and then add a reference to that application from any other applications containing artifacts that depend on it.</span></span> <span data-ttu-id="c6ac5-117">アプリケーションへの参照を追加すると、アプリケーション内のアイテムで、参照先アプリケーション内の任意のアイテムを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-117">When you add a reference to an application, artifacts in the application can use any artifacts in the application that it references.</span></span> <span data-ttu-id="c6ac5-118">参照を追加する方法の詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](http://go.microsoft.com/fwlink/?LinkID=155011)(<http://go.microsoft.com/fwlink/?LinkID=155011>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-118">For instructions on adding a reference, see [How to Add a Reference to Another Application](http://go.microsoft.com/fwlink/?LinkID=155011) (<http://go.microsoft.com/fwlink/?LinkID=155011>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
   <span data-ttu-id="c6ac5-119">BizTalk アプリケーション内のアイテムを更新するためのタスクのチェックリストについては、次を参照してください。[チェックリスト: BizTalk アプリケーション内のアイテムの更新](http://go.microsoft.com/fwlink/?LinkId=155647)(<http://go.microsoft.com/fwlink/?LinkId=155647>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="c6ac5-119">For a checklist of tasks for updating artifacts in a BizTalk application, see [Checklist: Update the Artifacts in a BizTalk Application](http://go.microsoft.com/fwlink/?LinkId=155647) (<http://go.microsoft.com/fwlink/?LinkId=155647>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ac5-120">参照</span><span class="sxs-lookup"><span data-stu-id="c6ac5-120">See Also</span></span>  
 [<span data-ttu-id="c6ac5-121">アプリケーションとアイテムの更新</span><span class="sxs-lookup"><span data-stu-id="c6ac5-121">Updating Applications and Artifacts</span></span>](../technical-guides/updating-applications-and-artifacts.md)