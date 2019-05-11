---
title: 成果物を追加または作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, creating
- applications, artifacts
ms.assetid: fea7487c-b5fa-457f-8c74-a20ea3a6df85
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0d206566cf47363ab52b540a55a5a3bc0d5014c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339091"
---
# <a name="how-to-create-or-add-an-artifact"></a><span data-ttu-id="9fab6-102">成果物を追加または作成する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-102">How to Create or Add an Artifact</span></span>
<span data-ttu-id="9fab6-103">BizTalk アプリケーションを作成した後は、ファイル システムからファイル ベースのアイテム (たとえば BizTalk アセンブリ、.NET アセンブリ、スクリプト、および証明書) を追加またはルール エンジン データベースからポリシーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9fab6-103">After you create a BizTalk application, you can add file-based artifacts (for example BizTalk assemblies, .NET assemblies, scripts, and certificates) from the file system or add policies from the Rule Engine database.</span></span> <span data-ttu-id="9fab6-104">作成することも送信ポート、送信ポート グループ、受信場所、およびアプリケーション内のポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="9fab6-104">You can also create send ports, send port groups, receive locations, and receive ports within the application.</span></span> <span data-ttu-id="9fab6-105">作成または成果物の追加は、BizTalk 管理データベースに追加します。</span><span class="sxs-lookup"><span data-stu-id="9fab6-105">Creating or adding artifacts adds them to the BizTalk Management database.</span></span> <span data-ttu-id="9fab6-106">できますし、展開するアプリケーションとそのアイテム 1 つのエンティティとして」の説明に従って[BizTalk アプリケーションの配置](../core/deploying-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="9fab6-106">You can then deploy the application and its artifacts as a single entity, as described in [Deploying BizTalk Applications](../core/deploying-biztalk-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fab6-107">特定の種類のアイテムは、BizTalk アプリケーションまたはグループ内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fab6-107">Certain types of artifacts must be unique in a BizTalk application or group.</span></span> <span data-ttu-id="9fab6-108">詳細については、次を参照してください。[成果物をする必要がありますする内で一意で、アプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)します。</span><span class="sxs-lookup"><span data-stu-id="9fab6-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="9fab6-109">手順の追加や各成果物の種類の作成については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fab6-109">For procedures on adding or creating each artifact type, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9fab6-110">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-110">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)  
  
-   [<span data-ttu-id="9fab6-111">送信ポート グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-111">How to Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="9fab6-112">作成する方法、受信ポート</span><span class="sxs-lookup"><span data-stu-id="9fab6-112">How to Create a Receive Port</span></span>](../core/how-to-create-a-receive-port.md)  
  
-   [<span data-ttu-id="9fab6-113">作成する方法、受信場所</span><span class="sxs-lookup"><span data-stu-id="9fab6-113">How to Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)  
  
-   [<span data-ttu-id="9fab6-114">アプリケーションにポリシーを追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-114">How to Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-115">BizTalk アセンブリをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-115">How to Add a BizTalk Assembly to an Application</span></span>](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-116">処理前または処理後のスクリプトをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-116">How to Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-117">アプリケーションにファイルを追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-117">How to Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-118">アプリケーションに証明書を追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-118">How to Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-119">アプリケーションに COM コンポーネントを追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-119">How to Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-120">.NET アセンブリをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-120">How to Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-121">アプリケーションに BAM アイテムを追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-121">How to Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="9fab6-122">アプリケーションにバインド ファイルを追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-122">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
> [!NOTE]
>  <span data-ttu-id="9fab6-123">追加するアイテムに非常に長いパス (たとえば、パスとファイル名) がある場合は、アプリケーションにアイテムを追加する操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="9fab6-123">If the artifact you are adding has a very long path (e.g., the path and file name), the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="9fab6-124">パスは 260 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="9fab6-124">A path can't exceed 260 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fab6-125">参照</span><span class="sxs-lookup"><span data-stu-id="9fab6-125">See Also</span></span>  
 <span data-ttu-id="9fab6-126">[作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="9fab6-126">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="9fab6-127">アプリケーションを 64 ビット アイテムを追加する方法</span><span class="sxs-lookup"><span data-stu-id="9fab6-127">How to Add a 64-Bit Artifact to an Application</span></span>](../core/how-to-add-a-64-bit-artifact-to-an-application.md)