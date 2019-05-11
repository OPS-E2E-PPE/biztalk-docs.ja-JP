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
ms.openlocfilehash: 09e59f51aa6d99fbd9b1351087a403350cc22a1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382210"
---
# <a name="importparties-command"></a><span data-ttu-id="bee02-102">ImportParties コマンド</span><span class="sxs-lookup"><span data-stu-id="bee02-102">ImportParties Command</span></span>
<span data-ttu-id="bee02-103">アプリケーションのアイテムのいずれかをインポートせず、構成データベース内のソース XML バインド ファイルからの企業間取引のパーティーと契約をインポートします。</span><span class="sxs-lookup"><span data-stu-id="bee02-103">Imports the business-to-business parties and agreements from a source XML binding file in the configuration database, without importing any of the application artifacts.</span></span> <span data-ttu-id="bee02-104">詳細については、次を参照してください。**解説**このトピックの「します。</span><span class="sxs-lookup"><span data-stu-id="bee02-104">For more information, see **Remarks** in this topic.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="bee02-105">このコマンドは、以降では新しい**[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**、およびそれ以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="bee02-105">This command is new starting with **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, and any newer versions.</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="bee02-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で生成されたバインド ファイルでは、アプリケーションが指定されません。</span><span class="sxs-lookup"><span data-stu-id="bee02-106">Binding files generated in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have an application specified.</span></span> <span data-ttu-id="bee02-107">これらは、既定のアプリケーションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="bee02-107">They are imported into the default application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="bee02-108">使用方法</span><span class="sxs-lookup"><span data-stu-id="bee02-108">Usage</span></span>  
  <span data-ttu-id="bee02-109">**BTSTask ImportParties -Source**:*value* **[-ExcludeEdiFallbackSettings]** [**-Server**:*value*] [**-Database**:*value*]</span><span class="sxs-lookup"><span data-stu-id="bee02-109">**BTSTask ImportParties -Source**:*value* [**-ExcludeEdiFallbackSettings**] [**-Server**:*value*] [**-Database**:*value*]</span></span>
  
## <a name="parameters"></a><span data-ttu-id="bee02-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bee02-110">Parameters</span></span>  
  
|<span data-ttu-id="bee02-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bee02-111">Parameter</span></span>|<span data-ttu-id="bee02-112">必須</span><span class="sxs-lookup"><span data-stu-id="bee02-112">Required</span></span>|<span data-ttu-id="bee02-113">値</span><span class="sxs-lookup"><span data-stu-id="bee02-113">Value</span></span>|  
|---|---|---|  
|<span data-ttu-id="bee02-114">**-ソース**</span><span class="sxs-lookup"><span data-stu-id="bee02-114">**-Source**</span></span> | <span data-ttu-id="bee02-115">必須</span><span class="sxs-lookup"><span data-stu-id="bee02-115">Required</span></span> | <span data-ttu-id="bee02-116">読み取る XML バインド ファイルのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="bee02-116">The path and file name of the XML binding file to read.</span></span>|
|<span data-ttu-id="bee02-117">**-ExcludeEdiFallbackSettings**</span><span class="sxs-lookup"><span data-stu-id="bee02-117">**-ExcludeEdiFallbackSettings**</span></span> | <span data-ttu-id="bee02-118">省略可</span><span class="sxs-lookup"><span data-stu-id="bee02-118">Optional</span></span> | <span data-ttu-id="bee02-119">指定した場合は、バインド ファイルから edi フォールバック (x12 および edifact) の設定を除外します。</span><span class="sxs-lookup"><span data-stu-id="bee02-119">If specified, it excludes edi fallback (x12 and edifact) settings from the binding file.</span></span>  |
| <span data-ttu-id="bee02-120">**-サーバー**</span><span class="sxs-lookup"><span data-stu-id="bee02-120">**-Server**</span></span> | <span data-ttu-id="bee02-121">省略可</span><span class="sxs-lookup"><span data-stu-id="bee02-121">Optional</span></span> | <span data-ttu-id="bee02-122">BizTalk 構成データベースをホストする SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="bee02-122">The name of SQL server hosting the BizTalk configuration database.</span></span> |
| <span data-ttu-id="bee02-123">**-データベース**</span><span class="sxs-lookup"><span data-stu-id="bee02-123">**-Database**</span></span> | <span data-ttu-id="bee02-124">省略可</span><span class="sxs-lookup"><span data-stu-id="bee02-124">Optional</span></span> | <span data-ttu-id="bee02-125">BizTalk 構成データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="bee02-125">The name of the BizTalk configuration database.</span></span> |

## <a name="sample"></a><span data-ttu-id="bee02-126">サンプル</span><span class="sxs-lookup"><span data-stu-id="bee02-126">Sample</span></span>
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a><span data-ttu-id="bee02-127">コメント</span><span class="sxs-lookup"><span data-stu-id="bee02-127">Remarks</span></span>
<span data-ttu-id="bee02-128">アプリケーション アイテムも、バインド ファイルにある場合、それらはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="bee02-128">If the binding file also has application artifacts, then they are not imported.</span></span> <span data-ttu-id="bee02-129">パーティーと契約だけがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="bee02-129">Only parties and agreements are imported.</span></span>