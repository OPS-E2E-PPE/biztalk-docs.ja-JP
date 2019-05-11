---
title: Visual Studio プロジェクト テンプレート |Microsoft Docs
description: .Btproj、BPEL、および BizTalk Server で使用される .btaproj Visual Studio テンプレートについて説明します
ms.custom: ''
ms.date: 11/07/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2b3d494-db80-4314-afcd-d08d5a26e211
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 412ee949494d6009032ace80cbf082a979afb492
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357902"
---
# <a name="biztalk-server-project-templates"></a><span data-ttu-id="7d924-103">BizTalk Server プロジェクト テンプレート</span><span class="sxs-lookup"><span data-stu-id="7d924-103">BizTalk Server Project Templates</span></span>

## <a name="overview"></a><span data-ttu-id="7d924-104">概要</span><span class="sxs-lookup"><span data-stu-id="7d924-104">Overview</span></span>
<span data-ttu-id="7d924-105">インストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、インストールで追加する BizTalk プロジェクト フォルダー、**新しいプロジェクト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7d924-105">When you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the installation adds the BizTalk Projects folder to the **New Project** dialog box.</span></span> <span data-ttu-id="7d924-106">BizTalk Projects フォルダーには、空の BizTalk Server プロジェクト、BizTalk Server BPEL インポート プロジェクト、および BizTalk Server アプリケーション プロジェクトを作成するためのテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d924-106">The BizTalk Projects folder contains templates for creating an empty BizTalk Server project, BizTalk Server BPEL Import project, and a BizTalk Server Application Project.</span></span>

## <a name="available-templates"></a><span data-ttu-id="7d924-107">使用可能なテンプレート</span><span class="sxs-lookup"><span data-stu-id="7d924-107">Available templates</span></span>
<span data-ttu-id="7d924-108">次の表では、これらのプロジェクト テンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7d924-108">The following table describes these project templates.</span></span>  


|                     <span data-ttu-id="7d924-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7d924-109">Use this</span></span>                      |                                                                                                                                                                   <span data-ttu-id="7d924-110">目的</span><span class="sxs-lookup"><span data-stu-id="7d924-110">To do this</span></span>                                                                                                                                                                   |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <span data-ttu-id="7d924-111">**空の BizTalk Server プロジェクト**</span><span class="sxs-lookup"><span data-stu-id="7d924-111">**Empty BizTalk Server Project**</span></span>          |                                                                                                                                                  <span data-ttu-id="7d924-112">新しい空の BizTalk Server プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7d924-112">Creates a new empty BizTalk Server project.</span></span>                                                                                                                                                   |
|      <span data-ttu-id="7d924-113">**BizTalk Server BPEL インポート プロジェクト**</span><span class="sxs-lookup"><span data-stu-id="7d924-113">**BizTalk Server BPEL Import Project**</span></span>       |                                                                                      <span data-ttu-id="7d924-114">Business Process Execution Language (BPEL)、Web サービス記述言語 (WSDL)、または XML スキーマ定義言語 (XSD) ファイルを BizTalk プロジェクトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="7d924-114">Imports Business Process Execution Language (BPEL), Web Services Description Language (WSDL), or XML Schema Definition Language (XSD) files into a BizTalk project.</span></span>                                                                                       |
| <span data-ttu-id="7d924-115">**BizTalk Server アプリケーション プロジェクト (.btaproj)**</span><span class="sxs-lookup"><span data-stu-id="7d924-115">**BizTalk Server Application Project (.btaproj)**</span></span> | <span data-ttu-id="7d924-116">以降で[!INCLUDE[bts2016](../includes/bts2016-md.md)] [Feature Pack 1](../core/configure-the-feature-pack.md)、またはそれ以降。</span><span class="sxs-lookup"><span data-stu-id="7d924-116">Starting with [!INCLUDE[bts2016](../includes/bts2016-md.md)] [Feature Pack 1](../core/configure-the-feature-pack.md), or later.</span></span> <br/><br/><span data-ttu-id="7d924-117">自動的に展開して、Visual Studio Team Services (VSTS) を使用してアプリケーションを更新するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7d924-117">Used to automatically deploy and update applications using Visual Studio Team Services (VSTS).</span></span> <span data-ttu-id="7d924-118">プロジェクトに含まれる、`BizTalkServerInventory.json`展開中に VSTS によって使用されるファイル。</span><span class="sxs-lookup"><span data-stu-id="7d924-118">The project contains a `BizTalkServerInventory.json` file that is used by VSTS during the deployment.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7d924-119">参照</span><span class="sxs-lookup"><span data-stu-id="7d924-119">See Also</span></span>  
 [<span data-ttu-id="7d924-120">BizTalk プロジェクトの操作</span><span class="sxs-lookup"><span data-stu-id="7d924-120">Working with BizTalk Projects</span></span>](../core/working-with-biztalk-projects.md)
