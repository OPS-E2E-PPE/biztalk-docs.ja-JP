---
title: AddApp コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 445784f1-505b-4259-a3f4-6f0d61578b1c
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb47b817c0f48cb82337afc6c82613fc35df28f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986579"
---
# <a name="addapp-command"></a><span data-ttu-id="fd28e-102">AddApp コマンド</span><span class="sxs-lookup"><span data-stu-id="fd28e-102">AddApp Command</span></span>
<span data-ttu-id="fd28e-103">BizTalk 管理データベースに新しい BizTalk アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd28e-103">Creates a new BizTalk application in the BizTalk Management database.</span></span> <span data-ttu-id="fd28e-104">作成したアプリケーションは、BizTalk Server 管理コンソールの [アプリケーション] ノードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd28e-104">You can view the application in the Applications node of the BizTalk Server Administration console.</span></span> <span data-ttu-id="fd28e-105">ことができますにアイテムを追加、アプリケーション、AddResource コマンドを使用して」の説明に従って[AddResource コマンド](../core/addresource-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="fd28e-105">You can add artifacts to the application by using the AddResource command, as described in [AddResource Command](../core/addresource-command.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="fd28e-106">使用方法</span><span class="sxs-lookup"><span data-stu-id="fd28e-106">Usage</span></span>  
 <span data-ttu-id="fd28e-107">**BTSTask AddApp/applicationname は:** *値*[**/Description:**<em>値</em>] **[/既定値]** [**/サーバー:**<em>値</em>] [**/database:**<em>値</em>]</span><span class="sxs-lookup"><span data-stu-id="fd28e-107">**BTSTask AddApp /ApplicationName:** *value* [**/Description:**<em>value</em>] [**/Default**] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="fd28e-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd28e-108">Parameters</span></span>  
  
|<span data-ttu-id="fd28e-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd28e-109">Parameter</span></span>|<span data-ttu-id="fd28e-110">必須</span><span class="sxs-lookup"><span data-stu-id="fd28e-110">Required</span></span>|<span data-ttu-id="fd28e-111">値</span><span class="sxs-lookup"><span data-stu-id="fd28e-111">Value</span></span>|  
|---------------|--------------|-----------|  
|<span data-ttu-id="fd28e-112">**/ApplicationName** (または **/A**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="fd28e-112">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="fd28e-113">はい</span><span class="sxs-lookup"><span data-stu-id="fd28e-113">Yes</span></span>|<span data-ttu-id="fd28e-114">追加する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="fd28e-114">Name of the BizTalk application to add.</span></span> <span data-ttu-id="fd28e-115">アプリケーション名にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd28e-115">If the application name includes spaces, it must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="fd28e-116">**/既定**(または **/Def**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="fd28e-116">**/Default** (or **/Def**, see Remarks)</span></span>|<span data-ttu-id="fd28e-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="fd28e-117">No</span></span>|<span data-ttu-id="fd28e-118">指定した場合、BizTalk グループの既定のアプリケーションになります。</span><span class="sxs-lookup"><span data-stu-id="fd28e-118">When specified, makes the new application the default application for the BizTalk group.</span></span>|  
|<span data-ttu-id="fd28e-119">**/説明**(または **/Des**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="fd28e-119">**/Description** (or **/Des**, see Remarks)</span></span>|<span data-ttu-id="fd28e-120">いいえ</span><span class="sxs-lookup"><span data-stu-id="fd28e-120">No</span></span>|<span data-ttu-id="fd28e-121">アプリケーションの説明。</span><span class="sxs-lookup"><span data-stu-id="fd28e-121">Description of the application.</span></span> <span data-ttu-id="fd28e-122">二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd28e-122">Must be enclosed in double quotation marks (").</span></span>|  
|<span data-ttu-id="fd28e-123">**/サーバー** (または **/S**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="fd28e-123">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="fd28e-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="fd28e-124">No</span></span>|<span data-ttu-id="fd28e-125">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="fd28e-125">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="fd28e-126">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="fd28e-126">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="fd28e-127">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="fd28e-127">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="fd28e-128">例 :</span><span class="sxs-lookup"><span data-stu-id="fd28e-128">Examples:</span></span><br /><br /> <span data-ttu-id="fd28e-129">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="fd28e-129">Server=MyServer</span></span><br /><br /> <span data-ttu-id="fd28e-130">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="fd28e-130">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="fd28e-131">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd28e-131">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="fd28e-132">**/データベース**(または **/Da**、「解説」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="fd28e-132">**/Database** (or **/Da**, see Remarks)</span></span>|<span data-ttu-id="fd28e-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="fd28e-133">No</span></span>|<span data-ttu-id="fd28e-134">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="fd28e-134">Name of the BizTalk Management database.</span></span> <span data-ttu-id="fd28e-135">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd28e-135">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="fd28e-136">サンプル</span><span class="sxs-lookup"><span data-stu-id="fd28e-136">Sample</span></span>  
 <span data-ttu-id="fd28e-137">**AddApp applicationname: myapplication/Description:「BizTalk アプリケーション」**</span><span class="sxs-lookup"><span data-stu-id="fd28e-137">**AddApp /ApplicationName:MyApplication /Description:"My BizTalk application"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd28e-138">コメント</span><span class="sxs-lookup"><span data-stu-id="fd28e-138">Remarks</span></span>  
 <span data-ttu-id="fd28e-139">パラメーターの大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="fd28e-139">Parameters are not case-sensitive.</span></span> <span data-ttu-id="fd28e-140">パラメーター名は、すべて入力する必要はありません。最初の数文字 (一意に特定できるだけの文字数) を入力するだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="fd28e-140">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd28e-141">参照</span><span class="sxs-lookup"><span data-stu-id="fd28e-141">See Also</span></span>  
 <span data-ttu-id="fd28e-142">[BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fd28e-142">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="fd28e-143">アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fd28e-143">How to Create an Application</span></span>](../core/how-to-create-an-application.md)