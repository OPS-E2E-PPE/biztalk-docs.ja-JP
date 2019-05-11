---
title: ListApps コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5eb0af-e153-4639-a6c0-56c951827c7c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 253f3cb365a89a6753be559b42de3c80dde5479c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380660"
---
# <a name="listapps-command"></a><span data-ttu-id="bd3a4-102">ListApps コマンド</span><span class="sxs-lookup"><span data-stu-id="bd3a4-102">ListApps Command</span></span>
<span data-ttu-id="bd3a4-103">指定した BizTalk 管理データベース内の BizTalk アプリケーションのすべての説明と名前をコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-103">Prints to the console the name and description of all of the BizTalk applications in the specified BizTalk Management database.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="bd3a4-104">使用方法</span><span class="sxs-lookup"><span data-stu-id="bd3a4-104">Usage</span></span>  
 <span data-ttu-id="bd3a4-105">**BTSTask ListApps** [**/Server:**<em>値</em>] [**/database:**<em>値</em>]</span><span class="sxs-lookup"><span data-stu-id="bd3a4-105">**BTSTask ListApps** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="bd3a4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd3a4-106">Parameters</span></span>  
  
|<span data-ttu-id="bd3a4-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd3a4-107">Parameter</span></span>|<span data-ttu-id="bd3a4-108">必須</span><span class="sxs-lookup"><span data-stu-id="bd3a4-108">Required</span></span>|<span data-ttu-id="bd3a4-109">説明</span><span class="sxs-lookup"><span data-stu-id="bd3a4-109">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="bd3a4-110">**/サーバー** (または **/S**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="bd3a4-110">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="bd3a4-111">いいえ</span><span class="sxs-lookup"><span data-stu-id="bd3a4-111">No</span></span>|<span data-ttu-id="bd3a4-112">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-112">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="bd3a4-113">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-113">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="bd3a4-114">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-114">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="bd3a4-115">例 :</span><span class="sxs-lookup"><span data-stu-id="bd3a4-115">Examples:</span></span><br /><br /> <span data-ttu-id="bd3a4-116">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="bd3a4-116">Server=MyServer</span></span><br /><br /> <span data-ttu-id="bd3a4-117">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="bd3a4-117">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="bd3a4-118">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-118">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="bd3a4-119">**/データベース**(または **/D**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="bd3a4-119">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="bd3a4-120">いいえ</span><span class="sxs-lookup"><span data-stu-id="bd3a4-120">No</span></span>|<span data-ttu-id="bd3a4-121">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-121">Name of the BizTalk Management database.</span></span> <span data-ttu-id="bd3a4-122">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-122">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="bd3a4-123">サンプル</span><span class="sxs-lookup"><span data-stu-id="bd3a4-123">Sample</span></span>  
 <span data-ttu-id="bd3a4-124">**BTSTask ListApps**</span><span class="sxs-lookup"><span data-stu-id="bd3a4-124">**BTSTask ListApps**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd3a4-125">コメント</span><span class="sxs-lookup"><span data-stu-id="bd3a4-125">Remarks</span></span>  
 <span data-ttu-id="bd3a4-126">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-126">Parameters are not case-sensitive.</span></span> <span data-ttu-id="bd3a4-127">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="bd3a4-127">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3a4-128">参照</span><span class="sxs-lookup"><span data-stu-id="bd3a4-128">See Also</span></span>  
 [<span data-ttu-id="bd3a4-129">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="bd3a4-129">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)