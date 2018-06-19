---
title: ImportSettings コマンド |Microsoft ドキュメント
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
ms.openlocfilehash: 9c609634422f8c8b5f2c1a96691fe4eda708e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257554"
---
# <a name="importsettings-command"></a><span data-ttu-id="35500-102">ImportSettings コマンド</span><span class="sxs-lookup"><span data-stu-id="35500-102">ImportSettings Command</span></span>
<span data-ttu-id="35500-103">BizTalk グループ、ホスト、またはホスト インスタンスの設定を、送信元 XML ファイルから構成データベースにインポートします。</span><span class="sxs-lookup"><span data-stu-id="35500-103">Imports the BizTalk group, host, or host instance settings from a source XML file to the configuration database.</span></span> <span data-ttu-id="35500-104">設定は、マッピング XML ファイル内にある場合と同じようにマップされます。</span><span class="sxs-lookup"><span data-stu-id="35500-104">The settings are mapped as they are in the mapping XML file.</span></span> <span data-ttu-id="35500-105">これらの設定はエクスポートされている」の説明に従って[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)または[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。</span><span class="sxs-lookup"><span data-stu-id="35500-105">These settings may have been exported as described in [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="35500-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="35500-106">Prerequisites</span></span>  
 <span data-ttu-id="35500-107">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35500-107">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="35500-108">使用方法</span><span class="sxs-lookup"><span data-stu-id="35500-108">Usage</span></span>  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="35500-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35500-109">Parameters</span></span>  
  
|<span data-ttu-id="35500-110">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="35500-110">**Parameter**</span></span>|<span data-ttu-id="35500-111">必須</span><span class="sxs-lookup"><span data-stu-id="35500-111">Required</span></span>|<span data-ttu-id="35500-112">値</span><span class="sxs-lookup"><span data-stu-id="35500-112">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="35500-113">**ソース**</span><span class="sxs-lookup"><span data-stu-id="35500-113">**-Source**</span></span>|<span data-ttu-id="35500-114">はい</span><span class="sxs-lookup"><span data-stu-id="35500-114">Yes</span></span>|<span data-ttu-id="35500-115">エクスポートされた設定 XML ファイルのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="35500-115">Path and file name of the exported settings XML file.</span></span>|  
|<span data-ttu-id="35500-116">**マップ**</span><span class="sxs-lookup"><span data-stu-id="35500-116">**-Map**</span></span>|<span data-ttu-id="35500-117">はい</span><span class="sxs-lookup"><span data-stu-id="35500-117">Yes</span></span>|<span data-ttu-id="35500-118">マッピング XML ファイルのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="35500-118">Path and file name of the mapping XML file.</span></span>|  
|<span data-ttu-id="35500-119">**-サーバー**</span><span class="sxs-lookup"><span data-stu-id="35500-119">**-Server**</span></span>|<span data-ttu-id="35500-120">省略可</span><span class="sxs-lookup"><span data-stu-id="35500-120">Optional</span></span>|<span data-ttu-id="35500-121">BizTalk 構成データベースをホストする SQL Server コンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="35500-121">The name of SQL Server computer hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="35500-122">**複数のデータベース**</span><span class="sxs-lookup"><span data-stu-id="35500-122">**-Database**</span></span>|<span data-ttu-id="35500-123">省略可</span><span class="sxs-lookup"><span data-stu-id="35500-123">Optional</span></span>|<span data-ttu-id="35500-124">BizTalk 構成データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="35500-124">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="35500-125">サンプル</span><span class="sxs-lookup"><span data-stu-id="35500-125">Sample</span></span>  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="35500-126">解説</span><span class="sxs-lookup"><span data-stu-id="35500-126">Remarks</span></span>  
 <span data-ttu-id="35500-127">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="35500-127">Parameters are not case-sensitive.</span></span> <span data-ttu-id="35500-128">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="35500-128">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35500-129">参照</span><span class="sxs-lookup"><span data-stu-id="35500-129">See Also</span></span>  
 [<span data-ttu-id="35500-130">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="35500-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)