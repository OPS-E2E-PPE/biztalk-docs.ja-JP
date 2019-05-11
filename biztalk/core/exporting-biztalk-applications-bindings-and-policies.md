---
title: BizTalk アプリケーション、バインド、およびポリシーのエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- exporting, policies
- bindings, exporting
- exporting, applications
- applications, exporting
- exporting, bindings
ms.assetid: ac101206-be49-47c9-a354-4f39e8b77acf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1847834ee04cf6b5f1d60398ea4310cac60b53c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388237"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="5bc9b-102">BizTalk アプリケーション、バインド、およびポリシーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="5bc9b-102">Exporting BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="5bc9b-103">このセクションでは、BizTalk アプリケーション、バインド、またはポリシーをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-103">This section describes how to export a BizTalk application, bindings, or policies.</span></span> <span data-ttu-id="5bc9b-104">BizTalk アプリケーションに含まれるアイテムの一部またはすべてをエクスポートすることができますか、バインドまたはポリシーをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-104">You can export some or all of the artifacts contained in a BizTalk application, or you can export only its bindings or policies.</span></span> <span data-ttu-id="5bc9b-105">アプリケーションをエクスポートするには、エクスポート用に選択したアプリケーションのアイテムを格納している Windows インストーラー (.msi) ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-105">Exporting an application creates a Windows Installer (.msi) file containing the application artifacts that you selected for export.</span></span> <span data-ttu-id="5bc9b-106">バインドまたはポリシーをエクスポートするには、バインドまたはポリシーの .xml ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-106">Exporting bindings or policies creates an .xml file of the bindings or policies.</span></span> <span data-ttu-id="5bc9b-107">このプロセスの背景については、次を参照してください。[何の動作とアイテムのエクスポート](../core/what-happens-when-artifacts-are-exported.md)します。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-107">For background information on this process, see [What Happens When Artifacts Are Exported](../core/what-happens-when-artifacts-are-exported.md).</span></span>  
  
 <span data-ttu-id="5bc9b-108">別の BizTalk グループをそのグループ内のアプリケーションのアイテムを含む新しいアプリケーションを作成するには、アプリケーションの .msi ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-108">You can import an application .msi file into another BizTalk group to create a new application that contains the application's artifacts in that group.</span></span> <span data-ttu-id="5bc9b-109">バインドまたはポリシーを使用する別の BizTalk アプリケーションには、バインドまたはポリシーの .xml ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-109">You can import a binding or policy .xml file into another BizTalk application to use the bindings or policies.</span></span> <span data-ttu-id="5bc9b-110">成果物をインポートする方法については、「[をインポートする BizTalk アプリケーション バインド、およびポリシー](../core/importing-biztalk-applications-bindings-and-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-110">How to import artifacts is described in [Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5bc9b-111">重要なビジネス データ接続、構成情報などを含めることは安全な場所にバインド ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5bc9b-111">Store binding files in a secure location, as they may contain critical business data such as connectivity and configuration information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bc9b-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5bc9b-112">In This Section</span></span>  
  
-   [<span data-ttu-id="5bc9b-113">BizTalk アプリケーションをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="5bc9b-113">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)  
  
-   [<span data-ttu-id="5bc9b-114">バインドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="5bc9b-114">Exporting Bindings</span></span>](../core/exporting-bindings6.md)  
  
-   [<span data-ttu-id="5bc9b-115">ポリシーをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="5bc9b-115">How to Export a Policy</span></span>](../core/how-to-export-a-policy.md)