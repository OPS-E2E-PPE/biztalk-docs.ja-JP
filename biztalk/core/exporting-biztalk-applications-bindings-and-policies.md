---
title: BizTalk アプリケーション、バインド、およびポリシーのエクスポート |Microsoft ドキュメント
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
ms.openlocfilehash: 5d6df445b0fefc132940a736870d66c62329ce60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245810"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a><span data-ttu-id="8bedc-102">BizTalk アプリケーション、バインド、およびポリシーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8bedc-102">Exporting BizTalk Applications, Bindings, and Policies</span></span>
<span data-ttu-id="8bedc-103">ここでは、BizTalk アプリケーション、バインド、またはポリシーをエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bedc-103">This section describes how to export a BizTalk application, bindings, or policies.</span></span> <span data-ttu-id="8bedc-104">BizTalk アプリケーションに含まれるアイテムの一部またはすべてをエクスポートすることも、バインドまたはポリシーだけをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8bedc-104">You can export some or all of the artifacts contained in a BizTalk application, or you can export only its bindings or policies.</span></span> <span data-ttu-id="8bedc-105">アプリケーションをエクスポートすると、Windows インストーラー (.msi) ファイルが作成されます。このファイルには、エクスポートするよう選択したアプリケーションのアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8bedc-105">Exporting an application creates a Windows Installer (.msi) file containing the application artifacts that you selected for export.</span></span> <span data-ttu-id="8bedc-106">バインドまたはポリシーをエクスポートすると、バインドまたはポリシーの .xml ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8bedc-106">Exporting bindings or policies creates an .xml file of the bindings or policies.</span></span> <span data-ttu-id="8bedc-107">このプロセスの基礎知識については、次を参照してください。[発生時に成果物はエクスポート内容](../core/what-happens-when-artifacts-are-exported.md)です。</span><span class="sxs-lookup"><span data-stu-id="8bedc-107">For background information on this process, see [What Happens When Artifacts Are Exported](../core/what-happens-when-artifacts-are-exported.md).</span></span>  
  
 <span data-ttu-id="8bedc-108">アプリケーションの .msi ファイルを別の BizTalk グループにインポートして、アプリケーションのアイテムをそのグループ内に含む新しいアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8bedc-108">You can import an application .msi file into another BizTalk group to create a new application that contains the application's artifacts in that group.</span></span> <span data-ttu-id="8bedc-109">バインドまたはポリシーの .xml ファイルを別の BizTalk アプリケーションにインポートすると、そのバインドまたはポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8bedc-109">You can import a binding or policy .xml file into another BizTalk application to use the bindings or policies.</span></span> <span data-ttu-id="8bedc-110">アイテムをインポートする方法については、「[をインポートする BizTalk アプリケーション バインド、およびポリシー](../core/importing-biztalk-applications-bindings-and-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="8bedc-110">How to import artifacts is described in [Importing BizTalk Applications, Bindings, and Policies](../core/importing-biztalk-applications-bindings-and-policies.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8bedc-111">バインド ファイルには接続情報や構成情報などの重要なビジネス データが含まれる可能性があるため、安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="8bedc-111">Store binding files in a secure location, as they may contain critical business data such as connectivity and configuration information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8bedc-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8bedc-112">In This Section</span></span>  
  
-   [<span data-ttu-id="8bedc-113">BizTalk アプリケーションをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="8bedc-113">How to Export a BizTalk Application</span></span>](../core/how-to-export-a-biztalk-application.md)  
  
-   [<span data-ttu-id="8bedc-114">バインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8bedc-114">Exporting Bindings</span></span>](../core/exporting-bindings6.md)  
  
-   [<span data-ttu-id="8bedc-115">ポリシーをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="8bedc-115">How to Export a Policy</span></span>](../core/how-to-export-a-policy.md)