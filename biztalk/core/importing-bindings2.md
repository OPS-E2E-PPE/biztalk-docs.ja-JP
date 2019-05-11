---
title: インポート Bindings2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, requirements
- importing, bindings
- bindings, importing
ms.assetid: 9e10bc04-aba8-430a-b8fd-de9399d54f88
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab3b7677336a2d10daf365d7bf58d3c90aa9f35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382528"
---
# <a name="importing-bindings"></a><span data-ttu-id="e9156-102">バインドのインポート</span><span class="sxs-lookup"><span data-stu-id="e9156-102">Importing Bindings</span></span>
<span data-ttu-id="e9156-103">このセクションの各トピックでは、バインドを BizTalk グループまたはアプリケーションにインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9156-103">The topics in this section describe how to import bindings into a BizTalk group or application.</span></span>  

 <span data-ttu-id="e9156-104">バインドをインポートする際は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9156-104">When importing bindings, bear in mind the following important points:</span></span>  

- <span data-ttu-id="e9156-105">**既存のバインドは上書きされます。**</span><span class="sxs-lookup"><span data-stu-id="e9156-105">**Existing bindings will be overwritten.**</span></span> <span data-ttu-id="e9156-106">インポートするバインドの名前が既存のバインドと同じ場合、既存のバインドは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e9156-106">If the bindings that you import have the same name as existing bindings, the existing bindings are overwritten.</span></span> <span data-ttu-id="e9156-107">また、バインド ファイルにパーティとエイリアスが含まれている場合、アプリケーション内にある同じ名前のパーティとエイリアスのバインドは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e9156-107">In addition, if the binding file contains parties and aliases, any bindings for parties and aliases of the same name that already exist in the application are overwritten.</span></span>  

- <span data-ttu-id="e9156-108">**グループのすべてのバインドは、一意である必要があります。**</span><span class="sxs-lookup"><span data-stu-id="e9156-108">**All bindings in a group must be unique.**</span></span> <span data-ttu-id="e9156-109">インポートするバインドと同じ名前のバインドがグループに存在する場合、インポート操作に失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9156-109">If a binding having the same name as one you are importing already exists in the group, the import operation will fail.</span></span>  

- <span data-ttu-id="e9156-110">**パスワードを再構成する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="e9156-110">**You must reconfigure passwords.**</span></span> <span data-ttu-id="e9156-111">セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e9156-111">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="e9156-112">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9156-112">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="e9156-113">BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。</span><span class="sxs-lookup"><span data-stu-id="e9156-113">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span> <span data-ttu-id="e9156-114">手順については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9156-114">For instructions, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span> <span data-ttu-id="e9156-115">参照してください[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9156-115">See also [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  

- <span data-ttu-id="e9156-116">**ホストは、グループ内に存在する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="e9156-116">**The host must exist in the group.**</span></span> <span data-ttu-id="e9156-117">バインドで指定されているホストに対応するホストは、バインドのインポート先の BizTalk グループ内に存在し、ホストの信頼レベルが一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9156-117">A host corresponding to the host specified in the bindings must already exist in the BizTalk group into which the bindings are imported and the host trust level must match.</span></span> <span data-ttu-id="e9156-118">そうでない場合、インポート操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9156-118">Otherwise, the import operation will fail.</span></span>  

- <span data-ttu-id="e9156-119">**バインドのインポートの動作は、バインドのソースによって異なります。**</span><span class="sxs-lookup"><span data-stu-id="e9156-119">**Binding import behavior depends on the source of the bindings.**</span></span> <span data-ttu-id="e9156-120">バインドのエクスポート元としては、アセンブリ、アプリケーション、グループが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e9156-120">The bindings may have been exported from an assembly, application, or group.</span></span> <span data-ttu-id="e9156-121">次の表に示すように、インポート操作の結果は、バインドがどこからエクスポートされたかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9156-121">Depending on from where the bindings were exported, the import operation may have different effects, as shown in the following table.</span></span>  


  |        <span data-ttu-id="e9156-122">バインドのエクスポート元</span><span class="sxs-lookup"><span data-stu-id="e9156-122">Origin of the bindings</span></span>         |                                                                        <span data-ttu-id="e9156-123">アプリケーションへのインポート</span><span class="sxs-lookup"><span data-stu-id="e9156-123">Importing into an application</span></span>                                                                        |                                                                                                     <span data-ttu-id="e9156-124">グループへのインポート</span><span class="sxs-lookup"><span data-stu-id="e9156-124">Importing into a group</span></span>                                                                                                      |
  |---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |  <span data-ttu-id="e9156-125">アセンブリからエクスポートされたバインド</span><span class="sxs-lookup"><span data-stu-id="e9156-125">Bindings exported from an assembly</span></span>   | <span data-ttu-id="e9156-126">指定されたアプリケーションには、バインド ファイルのエクスポート元アセンブリと同じ名前のアセンブリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9156-126">The specified application in must contain an assembly having the same name as the assembly from which the binding file was exported.</span></span> <span data-ttu-id="e9156-127">それ以外の場合、インポート操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9156-127">Otherwise, the import operation fails.</span></span> |                        <span data-ttu-id="e9156-128">グループには、バインド ファイルのエクスポート元のアセンブリおよびアプリケーションと同じ名前のアセンブリおよびアプリケーションが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9156-128">The group must contain an assembly and an application having the same name as the assembly and application from which the binding file was exported.</span></span> <span data-ttu-id="e9156-129">それ以外の場合、インポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9156-129">Otherwise, the import fails.</span></span>                        |
  | <span data-ttu-id="e9156-130">アプリケーションからエクスポートされたバインド</span><span class="sxs-lookup"><span data-stu-id="e9156-130">Bindings exported from an application</span></span> |            <span data-ttu-id="e9156-131">バインド ファイルのエクスポート元アプリケーションは、指定されたアプリケーションと同じ名前であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9156-131">The application from which the binding file was exported must have the same name as the specified application.</span></span> <span data-ttu-id="e9156-132">それ以外の場合、インポート操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9156-132">Otherwise, the import operation fails.</span></span>            |                <span data-ttu-id="e9156-133">バインド ファイルのエクスポート元アプリケーションは、バインドをインポートするグループのアプリケーションと同じ名前であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9156-133">The application from which the binding file was exported must have the same name as an application in the group into which you are importing the bindings.</span></span> <span data-ttu-id="e9156-134">それ以外の場合、インポート操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9156-134">Otherwise, the import operation fails.</span></span>                |
  |    <span data-ttu-id="e9156-135">グループからエクスポートされたバインド</span><span class="sxs-lookup"><span data-stu-id="e9156-135">Bindings exported from a group</span></span>     | <span data-ttu-id="e9156-136">バインド ファイルのエクスポート元グループには、指定されたアプリケーションと同じ名前のアプリケーションが存在していることが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9156-136">The group from which the binding file was exported must include an application that has the same name as the specified application.</span></span> <span data-ttu-id="e9156-137">それ以外の場合、インポート操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9156-137">Otherwise, the import operation fails.</span></span>  | <span data-ttu-id="e9156-138">バインドのインポートは、対応するアプリケーション間で行われます。</span><span class="sxs-lookup"><span data-stu-id="e9156-138">Bindings are imported for corresponding applications.</span></span> <span data-ttu-id="e9156-139">つまり、エクスポート元グループにおけるアプリケーションのバインドは、現在のグループで同じ名前を持つアプリケーションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e9156-139">In other words, the bindings of an application in the group from which bindings were exported are imported into an application having the same name in the current group.</span></span> |


- <span data-ttu-id="e9156-140">**アダプターの Name 属性が正しくない可能性があります。**</span><span class="sxs-lookup"><span data-stu-id="e9156-140">**The Name attribute for an adapter may be incorrect.**</span></span> <span data-ttu-id="e9156-141">バインド ファイルにアダプターの設定が含まれている場合は、バインド ファイル内に指定されている TransportType 要素の Name 属性の値が、BizTalk Server 管理コンソールでアダプターに設定されている名前と同じであることを確認してください ([プラットフォームの設定]、[アダプター] の順にクリックします)。</span><span class="sxs-lookup"><span data-stu-id="e9156-141">If the binding file includes settings for an adapter, verify that the Name attribute of the TransportType element in the binding file is the same as that configured for the adapter in the BizTalk Server Administration console (under Platform Settings > Adapters).</span></span>  

   <span data-ttu-id="e9156-142">バインドをインポートするときに、ケースあることを確認する必要があります具体的には、 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] BizTalk Server にします。</span><span class="sxs-lookup"><span data-stu-id="e9156-142">In particular, you should verify that this is the case when importing bindings from [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to BizTalk Server.</span></span> <span data-ttu-id="e9156-143">名前が異なると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9156-143">Some transports for which this may be an issue are as follows:</span></span>  

  -   <span data-ttu-id="e9156-144">MQS</span><span class="sxs-lookup"><span data-stu-id="e9156-144">MQS</span></span>  

  -   <span data-ttu-id="e9156-145">MSMQ (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="e9156-145">MSMQ</span></span>  

  -   <span data-ttu-id="e9156-146">POP3</span><span class="sxs-lookup"><span data-stu-id="e9156-146">POP3</span></span>  

  -   <span data-ttu-id="e9156-147">Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="e9156-147">Windows SharePoint Services</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="e9156-148">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e9156-148">In This Section</span></span>  

-   [<span data-ttu-id="e9156-149">BizTalk グループにバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="e9156-149">How to Import Bindings into a BizTalk Group</span></span>](../core/how-to-import-bindings-into-a-biztalk-group.md)  

-   [<span data-ttu-id="e9156-150">BizTalk アプリケーションにバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="e9156-150">How to Import Bindings into a BizTalk Application</span></span>](../core/how-to-import-bindings-into-a-biztalk-application.md)  

-   [<span data-ttu-id="e9156-151">Edi-as2 ソリューションのバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="e9156-151">How to Import Bindings for an EDI-AS2 Solution</span></span>](../core/how-to-import-bindings-for-an-edi-as2-solution.md)