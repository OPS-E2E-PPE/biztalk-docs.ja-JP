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
ms.openlocfilehash: 0206471feefe8ffe52ec2045ede865bb064ea452
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974011"
---
# <a name="listapps-command"></a><span data-ttu-id="843fc-102">ListApps コマンド</span><span class="sxs-lookup"><span data-stu-id="843fc-102">ListApps Command</span></span>
<span data-ttu-id="843fc-103">指定された BizTalk 管理データベースに存在するすべての BizTalk アプリケーションについて、名前と説明をコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="843fc-103">Prints to the console the name and description of all of the BizTalk applications in the specified BizTalk Management database.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="843fc-104">使用方法</span><span class="sxs-lookup"><span data-stu-id="843fc-104">Usage</span></span>  
 <span data-ttu-id="843fc-105">**BTSTask ListApps** [**/Server:**<em>値</em>] [**/database:**<em>値</em>]</span><span class="sxs-lookup"><span data-stu-id="843fc-105">**BTSTask ListApps** [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="843fc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="843fc-106">Parameters</span></span>  
  
|<span data-ttu-id="843fc-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="843fc-107">Parameter</span></span>|<span data-ttu-id="843fc-108">必須</span><span class="sxs-lookup"><span data-stu-id="843fc-108">Required</span></span>|<span data-ttu-id="843fc-109">説明</span><span class="sxs-lookup"><span data-stu-id="843fc-109">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="843fc-110">**/サーバー** (または **/S**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="843fc-110">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="843fc-111">いいえ</span><span class="sxs-lookup"><span data-stu-id="843fc-111">No</span></span>|<span data-ttu-id="843fc-112">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="843fc-112">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="843fc-113">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="843fc-113">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="843fc-114">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="843fc-114">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="843fc-115">例 :</span><span class="sxs-lookup"><span data-stu-id="843fc-115">Examples:</span></span><br /><br /> <span data-ttu-id="843fc-116">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="843fc-116">Server=MyServer</span></span><br /><br /> <span data-ttu-id="843fc-117">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="843fc-117">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="843fc-118">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="843fc-118">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="843fc-119">**/データベース**(または **/D**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="843fc-119">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="843fc-120">いいえ</span><span class="sxs-lookup"><span data-stu-id="843fc-120">No</span></span>|<span data-ttu-id="843fc-121">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="843fc-121">Name of the BizTalk Management database.</span></span> <span data-ttu-id="843fc-122">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="843fc-122">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="843fc-123">サンプル</span><span class="sxs-lookup"><span data-stu-id="843fc-123">Sample</span></span>  
 <span data-ttu-id="843fc-124">**BTSTask ListApps**</span><span class="sxs-lookup"><span data-stu-id="843fc-124">**BTSTask ListApps**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="843fc-125">コメント</span><span class="sxs-lookup"><span data-stu-id="843fc-125">Remarks</span></span>  
 <span data-ttu-id="843fc-126">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="843fc-126">Parameters are not case-sensitive.</span></span> <span data-ttu-id="843fc-127">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="843fc-127">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843fc-128">参照</span><span class="sxs-lookup"><span data-stu-id="843fc-128">See Also</span></span>  
 [<span data-ttu-id="843fc-129">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="843fc-129">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)