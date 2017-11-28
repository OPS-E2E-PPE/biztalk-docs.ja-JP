---
title: "作成して、BizTalk アプリケーションの変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], modifying
- managing [applications], creating
- applications, modifying
- applications, creating
- modifying, applications
- creating, applications
ms.assetid: d6c9ff3a-3903-40ec-bcaa-e46cbaf8a58d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5daa9630fb8ad742d34421478a19081ad5c83f50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-modifying-biztalk-applications"></a><span data-ttu-id="f876d-102">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="f876d-102">Creating and Modifying BizTalk Applications</span></span>
<span data-ttu-id="f876d-103">ここでは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、BizTalk アプリケーションを作成、構成、および変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f876d-103">This section describes how to use the BizTalk Server Administration console or the BTSTask command-line tool to create, configure, and modify BizTalk applications.</span></span>  
  
 <span data-ttu-id="f876d-104">作成に関する背景情報については、管理、配置、および BizTalk アプリケーションの更新を参照してください[Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)です。</span><span class="sxs-lookup"><span data-stu-id="f876d-104">For background information on creating, managing, deploying, and updating BizTalk applications, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="f876d-105">それらのプロパティの編集など、アイテムを管理する方法についてを参照してください。[成果物の管理](../core/managing-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="f876d-105">For information about managing artifacts, including editing their properties, see [Managing Artifacts](../core/managing-artifacts.md).</span></span> <span data-ttu-id="f876d-106">BizTalk アプリケーションの展開方法の詳細については、次を参照してください。 [BizTalk アプリケーションの配置](../core/deploying-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="f876d-106">For instructions on deploying BizTalk applications, see [Deploying BizTalk Applications](../core/deploying-biztalk-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f876d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f876d-107">In This Section</span></span>  
  
-   [<span data-ttu-id="f876d-108">アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-108">How to Create an Application</span></span>](../core/how-to-create-an-application.md)  
  
-   [<span data-ttu-id="f876d-109">アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-109">How to Configure an Application</span></span>](../core/how-to-configure-an-application.md)  
  
-   [<span data-ttu-id="f876d-110">アプリケーションの名前を変更する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-110">How to Change the Name of an Application</span></span>](../core/how-to-change-the-name-of-an-application.md)  
  
-   [<span data-ttu-id="f876d-111">成果物を追加または作成する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-111">How to Create or Add an Artifact</span></span>](../core/how-to-create-or-add-an-artifact.md)  
  
-   [<span data-ttu-id="f876d-112">Readme ファイルにリンクする方法</span><span class="sxs-lookup"><span data-stu-id="f876d-112">How to Link to a Readme File</span></span>](../core/how-to-link-to-a-readme-file.md)  
  
-   [<span data-ttu-id="f876d-113">アプリケーションを 64 ビット アイテムを追加する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-113">How to Add a 64-Bit Artifact to an Application</span></span>](../core/how-to-add-a-64-bit-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="f876d-114">既定のアプリケーションを変更する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-114">How to Change the Default Application</span></span>](../core/how-to-change-the-default-application.md)  
  
-   [<span data-ttu-id="f876d-115">別のアプリケーションへの参照を追加する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-115">How to Add a Reference to Another Application</span></span>](../core/how-to-add-a-reference-to-another-application.md)  
  
-   [<span data-ttu-id="f876d-116">アプリケーションの参照を表示する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-116">How to View the References of an Application</span></span>](../core/how-to-view-the-references-of-an-application.md)  
  
-   [<span data-ttu-id="f876d-117">別のアプリケーションへの参照を削除する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-117">How to Remove a Reference to Another Application</span></span>](../core/how-to-remove-a-reference-to-another-application.md)  
  
-   [<span data-ttu-id="f876d-118">別のアプリケーションにアイテムを移動する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-118">How to Move an Artifact to a Different Application</span></span>](../core/how-to-move-an-artifact-to-a-different-application.md)  
  
-   [<span data-ttu-id="f876d-119">アプリケーションからアイテムを削除する方法</span><span class="sxs-lookup"><span data-stu-id="f876d-119">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)