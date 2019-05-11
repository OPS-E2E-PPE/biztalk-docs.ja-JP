---
title: ImportSettings コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040e0d827fd8039433ed950119e6c7b2d0ee3a9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332162"
---
# <a name="importsettings-command"></a><span data-ttu-id="75533-102">ImportSettings コマンド</span><span class="sxs-lookup"><span data-stu-id="75533-102">ImportSettings Command</span></span>
<span data-ttu-id="75533-103">構成データベースをソース XML ファイルから BizTalk グループ、ホスト、またはホスト インスタンスの設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="75533-103">Imports the BizTalk group, host, or host instance settings from a source XML file to the configuration database.</span></span> <span data-ttu-id="75533-104">設定は、マッピング XML ファイルのようにマップされます。</span><span class="sxs-lookup"><span data-stu-id="75533-104">The settings are mapped as they are in the mapping XML file.</span></span> <span data-ttu-id="75533-105">これらの設定がエクスポートされました」の説明に従って[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)または[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。</span><span class="sxs-lookup"><span data-stu-id="75533-105">These settings may have been exported as described in [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="75533-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="75533-106">Prerequisites</span></span>  
 <span data-ttu-id="75533-107">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="75533-107">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="75533-108">使用方法</span><span class="sxs-lookup"><span data-stu-id="75533-108">Usage</span></span>  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="75533-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75533-109">Parameters</span></span>  
  
|<span data-ttu-id="75533-110">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="75533-110">**Parameter**</span></span>|<span data-ttu-id="75533-111">必須</span><span class="sxs-lookup"><span data-stu-id="75533-111">Required</span></span>|<span data-ttu-id="75533-112">値</span><span class="sxs-lookup"><span data-stu-id="75533-112">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="75533-113">**-ソース**</span><span class="sxs-lookup"><span data-stu-id="75533-113">**-Source**</span></span>|<span data-ttu-id="75533-114">はい</span><span class="sxs-lookup"><span data-stu-id="75533-114">Yes</span></span>|<span data-ttu-id="75533-115">エクスポートされた設定 XML ファイルのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="75533-115">Path and file name of the exported settings XML file.</span></span>|  
|<span data-ttu-id="75533-116">**-マップ**</span><span class="sxs-lookup"><span data-stu-id="75533-116">**-Map**</span></span>|<span data-ttu-id="75533-117">はい</span><span class="sxs-lookup"><span data-stu-id="75533-117">Yes</span></span>|<span data-ttu-id="75533-118">マッピング XML ファイルのパスとファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="75533-118">Path and file name of the mapping XML file.</span></span>|  
|<span data-ttu-id="75533-119">**-サーバー**</span><span class="sxs-lookup"><span data-stu-id="75533-119">**-Server**</span></span>|<span data-ttu-id="75533-120">省略可</span><span class="sxs-lookup"><span data-stu-id="75533-120">Optional</span></span>|<span data-ttu-id="75533-121">BizTalk 構成データベースをホストする SQL Server コンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="75533-121">The name of SQL Server computer hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="75533-122">**-データベース**</span><span class="sxs-lookup"><span data-stu-id="75533-122">**-Database**</span></span>|<span data-ttu-id="75533-123">省略可</span><span class="sxs-lookup"><span data-stu-id="75533-123">Optional</span></span>|<span data-ttu-id="75533-124">BizTalk 構成データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="75533-124">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="75533-125">サンプル</span><span class="sxs-lookup"><span data-stu-id="75533-125">Sample</span></span>  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="75533-126">コメント</span><span class="sxs-lookup"><span data-stu-id="75533-126">Remarks</span></span>  
 <span data-ttu-id="75533-127">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="75533-127">Parameters are not case-sensitive.</span></span> <span data-ttu-id="75533-128">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="75533-128">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75533-129">参照</span><span class="sxs-lookup"><span data-stu-id="75533-129">See Also</span></span>  
 [<span data-ttu-id="75533-130">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="75533-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)