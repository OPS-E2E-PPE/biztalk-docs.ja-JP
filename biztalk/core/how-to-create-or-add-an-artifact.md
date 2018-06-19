---
title: 成果物を追加または作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: b231cdf6a25c4ca316c9620ee789e6e3a715fd6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249490"
---
# <a name="how-to-create-or-add-an-artifact"></a><span data-ttu-id="04a0c-102">アイテムを作成または追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-102">How to Create or Add an Artifact</span></span>
<span data-ttu-id="04a0c-103">BizTalk アプリケーションを作成した後は、ファイル システムからファイル ベースのアイテム (BizTalk アセンブリ、.NET アセンブリ、スクリプト、証明書など) を追加したり、ルール エンジン データベースからポリシーを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="04a0c-103">After you create a BizTalk application, you can add file-based artifacts (for example BizTalk assemblies, .NET assemblies, scripts, and certificates) from the file system or add policies from the Rule Engine database.</span></span> <span data-ttu-id="04a0c-104">また、送信ポート、送信ポート グループ、受信場所、および受信ポートをアプリケーション内に作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="04a0c-104">You can also create send ports, send port groups, receive locations, and receive ports within the application.</span></span> <span data-ttu-id="04a0c-105">アイテムを作成または追加すると、そのアイテムは BizTalk 管理データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="04a0c-105">Creating or adding artifacts adds them to the BizTalk Management database.</span></span> <span data-ttu-id="04a0c-106">できますし、展開するアプリケーションとそのアイテム 1 つのエンティティとして」の説明に従って[BizTalk アプリケーションの配置](../core/deploying-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="04a0c-106">You can then deploy the application and its artifacts as a single entity, as described in [Deploying BizTalk Applications](../core/deploying-biztalk-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04a0c-107">特定の種類のアイテムは、BizTalk アプリケーションまたはグループ内で一意であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="04a0c-107">Certain types of artifacts must be unique in a BizTalk application or group.</span></span> <span data-ttu-id="04a0c-108">詳細については、次を参照してください。[成果物をする必要がありますする内で一意のアプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="04a0c-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="04a0c-109">各アイテムの種類を追加または作成する手順については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04a0c-109">For procedures on adding or creating each artifact type, see the following topics:</span></span>  
  
-   [<span data-ttu-id="04a0c-110">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-110">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)  
  
-   [<span data-ttu-id="04a0c-111">送信ポート グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-111">How to Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="04a0c-112">作成する方法、受信ポート</span><span class="sxs-lookup"><span data-stu-id="04a0c-112">How to Create a Receive Port</span></span>](../core/how-to-create-a-receive-port.md)  
  
-   [<span data-ttu-id="04a0c-113">作成する方法、受信場所</span><span class="sxs-lookup"><span data-stu-id="04a0c-113">How to Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)  
  
-   [<span data-ttu-id="04a0c-114">アプリケーションにポリシーを追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-114">How to Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-115">BizTalk アセンブリをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-115">How to Add a BizTalk Assembly to an Application</span></span>](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-116">前または処理後のスクリプトをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-116">How to Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-117">アプリケーションにファイルを追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-117">How to Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-118">アプリケーションに証明書を追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-118">How to Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-119">アプリケーションに COM コンポーネントを追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-119">How to Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-120">.NET アセンブリをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-120">How to Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-121">アプリケーションに BAM アイテムを追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-121">How to Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="04a0c-122">バインド ファイルをアプリケーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-122">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
> [!NOTE]
>  <span data-ttu-id="04a0c-123">追加するアイテムのパス (パスとファイル名など) が極端に長いと、アイテムをアプリケーションに追加するときにエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="04a0c-123">If the artifact you are adding has a very long path (e.g., the path and file name), the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="04a0c-124">パスに使用できるのは 260 文字までです。</span><span class="sxs-lookup"><span data-stu-id="04a0c-124">A path can't exceed 260 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a0c-125">参照</span><span class="sxs-lookup"><span data-stu-id="04a0c-125">See Also</span></span>  
 <span data-ttu-id="04a0c-126">[作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="04a0c-126">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="04a0c-127">アプリケーションを 64 ビット アイテムを追加する方法</span><span class="sxs-lookup"><span data-stu-id="04a0c-127">How to Add a 64-Bit Artifact to an Application</span></span>](../core/how-to-add-a-64-bit-artifact-to-an-application.md)