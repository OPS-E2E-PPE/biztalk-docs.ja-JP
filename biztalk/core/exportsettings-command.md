---
title: ExportSettings コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa34dab1-c854-473e-a693-43ba45624e16
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a521ec09017e1ea529dbeb097ce119edee69f7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388208"
---
# <a name="exportsettings-command"></a><span data-ttu-id="cede1-102">ExportSettings コマンド</span><span class="sxs-lookup"><span data-stu-id="cede1-102">ExportSettings Command</span></span>
<span data-ttu-id="cede1-103">ExportSettings コマンドで、XML ファイルに BizTalk Server の構成から BizTalk Server 設定をエクスポートするデータベースします。</span><span class="sxs-lookup"><span data-stu-id="cede1-103">The ExportSettings command nables you to export the BizTalk Server settings from a BizTalk Server configuration database to an XML file.</span></span> <span data-ttu-id="cede1-104">別の環境でこれらの設定をインポートすることができますし、[インポート BizTalk の設定を使用して設定ダッシュ ボード方法](../core/how-to-import-biztalk-settings-using-settings-dashboard.md)または[BTSTask を使用して BizTalk の設定のインポート方法](../core/how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="cede1-104">You can then import these settings in another environment as described in [How to Import BizTalk Settings Using Settings Dashboard](../core/how-to-import-biztalk-settings-using-settings-dashboard.md) or [How to Import BizTalk Settings Using BTSTask](../core/how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cede1-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="cede1-105">Prerequisites</span></span>  
 <span data-ttu-id="cede1-106">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cede1-106">To perform this operation, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="cede1-107">使用方法</span><span class="sxs-lookup"><span data-stu-id="cede1-107">Usage</span></span>  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a><span data-ttu-id="cede1-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cede1-108">Parameters</span></span>  
  
|<span data-ttu-id="cede1-109">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="cede1-109">**Parameter**</span></span>|<span data-ttu-id="cede1-110">必須</span><span class="sxs-lookup"><span data-stu-id="cede1-110">Required</span></span>|<span data-ttu-id="cede1-111">値</span><span class="sxs-lookup"><span data-stu-id="cede1-111">Value</span></span>|  
|-------------------|--------------|-----------|  
|<span data-ttu-id="cede1-112">**変換先**</span><span class="sxs-lookup"><span data-stu-id="cede1-112">**-Destination**</span></span>|<span data-ttu-id="cede1-113">はい</span><span class="sxs-lookup"><span data-stu-id="cede1-113">Yes</span></span>|<span data-ttu-id="cede1-114">書き込む XML ファイルのパスとファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="cede1-114">Path and file name of the XML file to write.</span></span>|  
|<span data-ttu-id="cede1-115">**-サーバー**</span><span class="sxs-lookup"><span data-stu-id="cede1-115">**-Server**</span></span>|<span data-ttu-id="cede1-116">省略可</span><span class="sxs-lookup"><span data-stu-id="cede1-116">Optional</span></span>|<span data-ttu-id="cede1-117">BizTalk 構成データベースをホストする SQL Server の名前。</span><span class="sxs-lookup"><span data-stu-id="cede1-117">The name of SQL Server hosting the BizTalk configuration database.</span></span>|  
|<span data-ttu-id="cede1-118">**-データベース**</span><span class="sxs-lookup"><span data-stu-id="cede1-118">**-Database**</span></span>|<span data-ttu-id="cede1-119">省略可</span><span class="sxs-lookup"><span data-stu-id="cede1-119">Optional</span></span>|<span data-ttu-id="cede1-120">BizTalk 構成データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="cede1-120">The name of the BizTalk configuration database.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="cede1-121">サンプル</span><span class="sxs-lookup"><span data-stu-id="cede1-121">Sample</span></span>  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a><span data-ttu-id="cede1-122">コメント</span><span class="sxs-lookup"><span data-stu-id="cede1-122">Remarks</span></span>  
 <span data-ttu-id="cede1-123">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="cede1-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="cede1-124">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="cede1-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cede1-125">参照</span><span class="sxs-lookup"><span data-stu-id="cede1-125">See Also</span></span>  
 [<span data-ttu-id="cede1-126">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="cede1-126">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)