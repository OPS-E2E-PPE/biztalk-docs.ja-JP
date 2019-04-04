---
title: ImportParties コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c25b913b6479b857fb7cee4aec10e6984f2195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998539"
---
# <a name="importparties-command"></a><span data-ttu-id="dfb4e-102">ImportParties コマンド</span><span class="sxs-lookup"><span data-stu-id="dfb4e-102">ImportParties Command</span></span>
<span data-ttu-id="dfb4e-103">アプリケーションのアイテムのいずれかをインポートせず、構成データベース内のソース XML バインド ファイルからの企業間取引のパーティーと契約をインポートします。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-103">Imports the business-to-business parties and agreements from a source XML binding file in the configuration database, without importing any of the application artifacts.</span></span> <span data-ttu-id="dfb4e-104">詳細については、**解説**このトピックの「を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-104">For more information, see **Remarks** in this topic.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="dfb4e-105">このコマンドは、以降では新しい**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**、およびそれ以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-105">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="dfb4e-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で生成されたバインド ファイルでは、アプリケーションが指定されません。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-106">Binding files generated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have an application specified.</span></span> <span data-ttu-id="dfb4e-107">これらは、既定のアプリケーションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-107">They are imported into the default application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="dfb4e-108">使用方法</span><span class="sxs-lookup"><span data-stu-id="dfb4e-108">Usage</span></span>  
  <span data-ttu-id="dfb4e-109">**BTSTask ImportParties-ソース**:*値\*\*\*[- ExcludeEdiFallbackSettings]*\* [**-サーバー**:*値*] [**-データベース**:*値*]</span><span class="sxs-lookup"><span data-stu-id="dfb4e-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="dfb4e-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dfb4e-110">Parameters</span></span>  
  
|<span data-ttu-id="dfb4e-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dfb4e-111">Parameter</span></span>|<span data-ttu-id="dfb4e-112">必須</span><span class="sxs-lookup"><span data-stu-id="dfb4e-112">Required</span></span>|<span data-ttu-id="dfb4e-113">値</span><span class="sxs-lookup"><span data-stu-id="dfb4e-113">Value</span></span>|  
|---|---|---|  
|<span data-ttu-id="dfb4e-114">**-ソース**</span><span class="sxs-lookup"><span data-stu-id="dfb4e-114">**-Source**</span></span> | <span data-ttu-id="dfb4e-115">必須</span><span class="sxs-lookup"><span data-stu-id="dfb4e-115">Required</span></span> | <span data-ttu-id="dfb4e-116">読み取る XML バインド ファイルのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-116">The path and file name of the XML binding file to read.</span></span>|
|<span data-ttu-id="dfb4e-117">**-ExcludeEdiFallbackSettings**</span><span class="sxs-lookup"><span data-stu-id="dfb4e-117">**-ExcludeEdiFallbackSettings**</span></span> | <span data-ttu-id="dfb4e-118">省略可</span><span class="sxs-lookup"><span data-stu-id="dfb4e-118">Optional</span></span> | <span data-ttu-id="dfb4e-119">指定した場合は、バインド ファイルから edi フォールバック (x12 および edifact) の設定を除外します。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-119">If specified, it excludes edi fallback (x12 and edifact) settings from the binding file.</span></span>  |
| <span data-ttu-id="dfb4e-120">**-サーバー**</span><span class="sxs-lookup"><span data-stu-id="dfb4e-120">**-Server**</span></span> | <span data-ttu-id="dfb4e-121">省略可</span><span class="sxs-lookup"><span data-stu-id="dfb4e-121">Optional</span></span> | <span data-ttu-id="dfb4e-122">BizTalk 構成データベースをホストする SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-122">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="dfb4e-123">**-データベース**</span><span class="sxs-lookup"><span data-stu-id="dfb4e-123">**-Database**</span></span> | <span data-ttu-id="dfb4e-124">省略可</span><span class="sxs-lookup"><span data-stu-id="dfb4e-124">Optional</span></span> | <span data-ttu-id="dfb4e-125">BizTalk 構成データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-125">The name of the BizTalk configuration database.</span></span> |

## <a name="sample"></a><span data-ttu-id="dfb4e-126">サンプル</span><span class="sxs-lookup"><span data-stu-id="dfb4e-126">Sample</span></span>
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a><span data-ttu-id="dfb4e-127">コメント</span><span class="sxs-lookup"><span data-stu-id="dfb4e-127">Remarks</span></span>
<span data-ttu-id="dfb4e-128">アプリケーション アイテムも、バインド ファイルにある場合、それらはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-128">If the binding file also has application artifacts, then they are not imported.</span></span> <span data-ttu-id="dfb4e-129">パーティーと契約だけがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="dfb4e-129">Only parties and agreements are imported.</span></span>