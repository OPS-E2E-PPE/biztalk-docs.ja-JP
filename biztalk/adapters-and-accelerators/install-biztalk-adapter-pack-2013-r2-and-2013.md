---
title: "BizTalk Adapter Pack 2013 R2 と 2013 のインストール |Microsoft ドキュメント"
description: "前提条件と BAP 2013 R2 および BizTalk Server に含まれている BAP 2013 をインストールする手順"
ms.custom: 
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9980953a-8d38-476f-af38-4f4214ba61f2
caps.latest.revision: "107"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d91e697504adf23585392c6c761bc13b300c3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-adapter-pack-2013-r2-and-2013"></a><span data-ttu-id="ae10d-103">BizTalk Adapter Pack 2013 R2 と 2013 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-103">Install BizTalk Adapter Pack 2013 R2 and 2013</span></span>
<span data-ttu-id="ae10d-104">このドキュメントには、Microsoft をインストールするには、ソフトウェア要件、および手順[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)](BAP) は、BizTalk Server 2013 に含まれているか、[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-104">This document lists the software requirements, and the steps to install the Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) included with BizTalk Server 2013 or [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)].</span></span>  
  
## <a name="change-log"></a><span data-ttu-id="ae10d-105">変更ログ</span><span class="sxs-lookup"><span data-stu-id="ae10d-105">Change Log</span></span>  
  
|<span data-ttu-id="ae10d-106">日付</span><span class="sxs-lookup"><span data-stu-id="ae10d-106">Date</span></span>|<span data-ttu-id="ae10d-107">変更</span><span class="sxs-lookup"><span data-stu-id="ae10d-107">Change</span></span>|  
|---|---|  
|<span data-ttu-id="ae10d-108">2016 年 3 月</span><span class="sxs-lookup"><span data-stu-id="ae10d-108">March 2016</span></span>|<span data-ttu-id="ae10d-109">**インストール後にしています.**Oracle.DataAccess.dll の新しいバージョンを使用する Oracle データベース アダプターを構成する手順を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-109">In **After installing…**, added steps to configure Oracle Database adapter to use the newer Oracle.DataAccess.dll version.</span></span>|  
  
<a name="BKMK_Prereqs"></a>   
## <a name="software-prerequisites"></a><span data-ttu-id="ae10d-110">ソフトウェアの前提条件</span><span class="sxs-lookup"><span data-stu-id="ae10d-110">Software prerequisites</span></span>  
 <span data-ttu-id="ae10d-111">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]から使用されることができます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-111">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be consumed from:</span></span>  
  
-   <span data-ttu-id="ae10d-112">.NET アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ae10d-112">A .NET application</span></span>  
  
-   <span data-ttu-id="ae10d-113">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-113">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="ae10d-114">ADO インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae10d-114">An ADO interface</span></span>  
  
-   <span data-ttu-id="ae10d-115">Microsoft SharePoint ポータル</span><span class="sxs-lookup"><span data-stu-id="ae10d-115">A Microsoft SharePoint portal</span></span>  
  
 <span data-ttu-id="ae10d-116">アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-116">Based on how you use the adapters, the required software varies.</span></span>  
  
### <a name="prerequisites-when-using-a-net-application"></a><span data-ttu-id="ae10d-117">.NET アプリケーションを使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="ae10d-117">Prerequisites when using a .NET application</span></span>  
<span data-ttu-id="ae10d-118">アダプターを使用する .NET アプリケーションの使用、開発用コンピューター (.NET アプリケーションを作成しているコンピューター) で、次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-118">When using a .NET application to consume the adapters, the following software is required on your development computer (the computer where you're creating the .NET application).</span></span> <span data-ttu-id="ae10d-119">この順で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-119">Install the software in the order listed.</span></span>
  
|<span data-ttu-id="ae10d-120">BizTalk Adapter Pack 2013 R2</span><span class="sxs-lookup"><span data-stu-id="ae10d-120">BizTalk Adapter Pack 2013 R2</span></span>|<span data-ttu-id="ae10d-121">BizTalk Adapter Pack 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-121">BizTalk Adapter Pack 2013</span></span>|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-122">R2 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-122"> R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1</span></span>|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-123">、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-123">, [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1</span></span>|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|<span data-ttu-id="ae10d-124">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-124">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="ae10d-125">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-125">Visual Studio 2013</span></span>|<span data-ttu-id="ae10d-126">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="ae10d-126">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|<span data-ttu-id="ae10d-127">エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-127">The enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-128">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-128">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|<span data-ttu-id="ae10d-129">エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-129">The enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-130">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-130">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|  

### <a name="prerequisites-when-using-a-biztalk-server"></a><span data-ttu-id="ae10d-131">BizTalk Server を使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="ae10d-131">Prerequisites when using a BizTalk Server</span></span>  
<span data-ttu-id="ae10d-132">BizTalk Server を使用して、アダプターを使用する、BizTalk Server で、次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-132">When using a BizTalk Server to consume the adapters, the following software is required on your BizTalk Server.</span></span> <span data-ttu-id="ae10d-133">この順で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-133">Install the software in the order listed.</span></span>
  
|<span data-ttu-id="ae10d-134">BizTalk Adapter Pack 2013 R2</span><span class="sxs-lookup"><span data-stu-id="ae10d-134">BizTalk Adapter Pack 2013 R2</span></span>|<span data-ttu-id="ae10d-135">BizTalk Adapter Pack 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-135">BizTalk Adapter Pack 2013</span></span>|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-136">R2 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-136"> R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1</span></span>|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-137">、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-137">, [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1</span></span>|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|<span data-ttu-id="ae10d-138">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-138">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="ae10d-139">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-139">Visual Studio 2013</span></span>|<span data-ttu-id="ae10d-140">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="ae10d-140">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="ae10d-141">インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-141">Install the [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="ae10d-142">インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-142">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span>|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="ae10d-143">インストール、[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-143">Install the [!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="ae10d-144">インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-144">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span>|  
|<span data-ttu-id="ae10d-145">BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="ae10d-145">BizTalk Server 2013 R2</span></span>|<span data-ttu-id="ae10d-146">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-146">BizTalk Server 2013</span></span>|  
|<span data-ttu-id="ae10d-147">エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-147">The enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-148">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-148">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|<span data-ttu-id="ae10d-149">エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-149">The enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-150">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-150">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|  

### <a name="prerequisites-when-using-ado"></a><span data-ttu-id="ae10d-151">ADO を使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="ae10d-151">Prerequisites when using ADO</span></span>  
 <span data-ttu-id="ae10d-152"> **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** と **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]**  ADO レイヤーが含まれます ( *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* と *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]* )。</span><span class="sxs-lookup"><span data-stu-id="ae10d-152">The **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** and **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** include an ADO layer (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* and *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*).</span></span> <span data-ttu-id="ae10d-153">この ADO レイヤーは、SAP システムまたは Siebel システムへの接続に、ADO.NET クライアントを記述する使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-153">This ADO layer can be used to write an ADO.NET client to connect to an SAP system or Siebel system.</span></span> <span data-ttu-id="ae10d-154">行えます ADO レイヤーで SQL Server Integration Services (SSIS) のインポートし、エクスポートのデータ、LOB アプリケーション、および SQL Server Reporting Services (SSRS) レポートを生成するデータ、LOB システムの表示にします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-154">You can also use the ADO layer with SQL Server Integration Services (SSIS) to import and export data from the LOB application, and SQL Server Reporting Services (SSRS) to generate reports to present data from the LOB systems.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae10d-155">ADO プロバイダーを使用して、SSRS でのみサポートされて、  *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]*です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-155">Using the ADO Provider with SSRS is supported only for the *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]*.</span></span>  
  
<span data-ttu-id="ae10d-156">使用するコンピューターで、次のソフトウェアが必要な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-156">The following software is required on the computer that uses the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] with an ADO interface.</span></span> <span data-ttu-id="ae10d-157">この順で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-157">Install the software in the order listed.</span></span>
  
|<span data-ttu-id="ae10d-158">BizTalk Adapter Pack 2013 R2</span><span class="sxs-lookup"><span data-stu-id="ae10d-158">BizTalk Adapter Pack 2013 R2</span></span>|<span data-ttu-id="ae10d-159">BizTalk Adapter Pack 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-159">BizTalk Adapter Pack 2013</span></span>|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-160">R2 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、Windows 8.1、Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-160"> R2, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], Windows 8.1, Windows 7 SP1</span></span>|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-161">、 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、Windows 8、Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-161">, [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1, Windows 8, Windows 7 SP1</span></span>|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|<span data-ttu-id="ae10d-162">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-162">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="ae10d-163">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-163">Visual Studio 2013</span></span>|<span data-ttu-id="ae10d-164">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="ae10d-164">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]<span data-ttu-id="ae10d-165">, [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-165">, [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]</span></span>|[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]<span data-ttu-id="ae10d-166">, [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-166">, [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span></span>|  
|<span data-ttu-id="ae10d-167">エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-167">The enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-168">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-168">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|<span data-ttu-id="ae10d-169">エンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-169">The enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-170">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-170">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>|  

### <a name="prerequisites-when-using-microsoft-sharepoint"></a><span data-ttu-id="ae10d-171">Microsoft SharePoint を使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="ae10d-171">Prerequisites when using Microsoft SharePoint</span></span>  
 <span data-ttu-id="ae10d-172">Microsoft SharePoint で、アダプターの使用の目的は、SharePoint portal の LOB アプリケーションからデータを表示です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-172">The goal of using the adapters with Microsoft SharePoint is to show data from an LOB application on a SharePoint portal.</span></span>  
  
<span data-ttu-id="ae10d-173">一般的なセットアップで、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SharePoint 1 台のコンピューターまたはできるさまざまなタスクの別のコンピューターを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-173">A typical setup with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] and SharePoint can be a single computer or use different computers for different tasks.</span></span> <span data-ttu-id="ae10d-174">次の表は、各コンピューターのソフトウェアの前提条件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-174">The following table summarizes the software prerequisites for each computer.</span></span> <span data-ttu-id="ae10d-175">1 台のコンピューターを使用している場合は、そのコンピューターのすべてのソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-175">If you are using a single computer, all the software is required on that computer.</span></span> <span data-ttu-id="ae10d-176">この順で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-176">Install the software in the order listed.</span></span>  
  
|<span data-ttu-id="ae10d-177">WCF アダプター サービス開発ウィザードを実行するコンピューター</span><span class="sxs-lookup"><span data-stu-id="ae10d-177">Computer where you run the WCF Adapter Service Development Wizard</span></span>|<span data-ttu-id="ae10d-178">WCF サービスをホストするコンピューター</span><span class="sxs-lookup"><span data-stu-id="ae10d-178">Computer where you host the WCF service</span></span>|<span data-ttu-id="ae10d-179">コンピューターの外部コンテンツ タイプを定義する SharePoint Designer を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-179">Computer where you can use the SharePoint Designer to define your External Content Types</span></span>|<span data-ttu-id="ae10d-180">LOB アプリケーションからの情報を提示する SharePoint を使用するコンピューター</span><span class="sxs-lookup"><span data-stu-id="ae10d-180">Computer where you use SharePoint to present the information from an LOB application</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="ae10d-181">**BAP 2013 R2**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-181">**BAP 2013 R2**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-182"> R2</span><span class="sxs-lookup"><span data-stu-id="ae10d-182"> R2</span></span><br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/><span data-ttu-id="ae10d-183">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ae10d-183">Windows 8.1</span></span><br/><span data-ttu-id="ae10d-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-184">Windows 7 SP1</span></span></li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li> <span data-ttu-id="ae10d-185">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="ae10d-185">Visual Studio 2013</span></span></li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="ae10d-186">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-186">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="ae10d-187">それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-187">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-188">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-188">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li></ul> <span data-ttu-id="ae10d-189">**BAP 2013**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-189">**BAP 2013**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]<span data-ttu-id="ae10d-190"> SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-190"> SP1</span></span><br/><span data-ttu-id="ae10d-191">Windows 8</span><span class="sxs-lookup"><span data-stu-id="ae10d-191">Windows 8</span></span><br/><span data-ttu-id="ae10d-192">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-192">Windows 7 SP1</span></span></li><li><span data-ttu-id="ae10d-193">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-193">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span></li><li><span data-ttu-id="ae10d-194">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="ae10d-194">Visual Studio 2012</span></span></li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="ae10d-195">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-195">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="ae10d-196">それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-196">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-197">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-197">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li></ul>|<span data-ttu-id="ae10d-198">**BAP 2013 R2**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-198">**BAP 2013 R2**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="ae10d-199"> R2</span><span class="sxs-lookup"><span data-stu-id="ae10d-199"> R2</span></span><br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/><span data-ttu-id="ae10d-200">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ae10d-200">Windows 8.1</span></span><br/><span data-ttu-id="ae10d-201">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-201">Windows 7 SP1</span></span></li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="ae10d-202">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-202">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="ae10d-203">それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-203">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-204">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-204">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li><li><span data-ttu-id="ae10d-205">オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。</span><span class="sxs-lookup"><span data-stu-id="ae10d-205">Internet Information Services (IIS) version that comes with the operating system.</span></span> <span data-ttu-id="ae10d-206">KB 224609 は、バージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-206">KB 224609 lists the versions.</span></span></li></ul><span data-ttu-id="ae10d-207">**BAP 2013**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-207">**BAP 2013**:</span></span><ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]<span data-ttu-id="ae10d-208"> SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-208"> SP1</span></span><br/><span data-ttu-id="ae10d-209">Windows 8</span><span class="sxs-lookup"><span data-stu-id="ae10d-209">Windows 8</span></span><br/><span data-ttu-id="ae10d-210">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="ae10d-210">Windows 7 SP1</span></span></li><li><span data-ttu-id="ae10d-211">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-211">Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</span></span></li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li><span data-ttu-id="ae10d-212">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-212">Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</span></span></li><li><span data-ttu-id="ae10d-213">それぞれのエンタープライズ アプリケーションのクライアントと関連付けられているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="ae10d-213">Respective enterprise application clients and associated software.</span></span> <span data-ttu-id="ae10d-214">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-214">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span></li><li><span data-ttu-id="ae10d-215">オペレーティング システムに付属しているインターネット インフォメーション サービス (IIS) バージョン。</span><span class="sxs-lookup"><span data-stu-id="ae10d-215">Internet Information Services (IIS) version that comes with the operating system.</span></span> <span data-ttu-id="ae10d-216">KB 224609 は、バージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-216">KB 224609 lists the versions.</span></span></li></ul>|<span data-ttu-id="ae10d-217">Microsoft Office SharePoint Server ソフトウェア開発キット (SDK)</span><span class="sxs-lookup"><span data-stu-id="ae10d-217">Microsoft Office SharePoint Server Software Development Kit (SDK)</span></span>|<span data-ttu-id="ae10d-218">Microsoft Office のサーバー インフラストラクチャを更新します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-218">Microsoft Office Servers Infrastructure Update.</span></span> <span data-ttu-id="ae10d-219">ダウンロード[http://go.microsoft.com/fwlink/?LinkId=128344](http://go.microsoft.com/fwlink/?LinkId=128344)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-219">Download at [http://go.microsoft.com/fwlink/?LinkId=128344](http://go.microsoft.com/fwlink/?LinkId=128344).</span></span>|  
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a><span data-ttu-id="ae10d-220">サポートされているエンタープライズ アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="ae10d-220">Supported enterprise application versions</span></span>  

<span data-ttu-id="ae10d-221">サポートされている特定の LOB システムのバージョンを表示する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください**[サポートされている行の基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-221">To see the specific LOB system versions that are supported by the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], see **[Supported Line-of-Business (LOB) systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**.</span></span> 

<span data-ttu-id="ae10d-222">ここでは、各アダプターに必要なすべてのクライアント Dll など、各アダプターの追加情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-222">This section lists any extra info for each adapter, such as any client DLLs required for each adapter.</span></span>  
  
### <a name="oracle-database-adapter"></a><span data-ttu-id="ae10d-223">Oracle Database アダプター</span><span class="sxs-lookup"><span data-stu-id="ae10d-223">Oracle Database adapter</span></span>  
  
-   <span data-ttu-id="ae10d-224">省略可能: 分散トランザクションを使用して Oracle データベースがある場合はインストール**Oracle Services for Microsoft Transaction Server** (Oracle クライアントのインストールの一部) アダプターのクライアントを実行している、コンピューター。</span><span class="sxs-lookup"><span data-stu-id="ae10d-224">Optional: If you use distributed transactions with the Oracle database, install **Oracle Services for Microsoft Transaction Server** (part of the Oracle client installation) on the computer running the adapter client.</span></span>  
  
-   <span data-ttu-id="ae10d-225">ODP.NET の最新バージョンで動作するアプリケーションをインストール、**ポリシー Dll**および GAC の Dll を登録します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-225">For your application to work with the most recent version of ODP.NET, install the **policy DLLs** and register the DLLs in the GAC.</span></span> <span data-ttu-id="ae10d-226">参照してください[.NET に関する FAQ の Oracle データ プロバイダー](http://www.oracle.com/technetwork/database/windows/faq-093106.html)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-226">See [Oracle Data Provider for .NET FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html).</span></span>  

### <a name="oracle-e-business-adapter"></a><span data-ttu-id="ae10d-227">Oracle E-Business アダプター</span><span class="sxs-lookup"><span data-stu-id="ae10d-227">Oracle E-Business adapter</span></span>  
  
-   <span data-ttu-id="ae10d-228">省略可能: Oracle データベースに分散トランザクションを使用するインストール**Oracle Services for Microsoft Transaction Server** (Oracle クライアントのインストールの一部) アダプターのクライアントを実行している、コンピューター。</span><span class="sxs-lookup"><span data-stu-id="ae10d-228">Optional: To use distributed transactions with the Oracle database, install **Oracle Services for Microsoft Transaction Server** (part of the Oracle client installation) on the computer running the adapter client.</span></span>  
  
-   <span data-ttu-id="ae10d-229">ODP.NET の最新バージョンで動作するアプリケーションをインストール、**ポリシー Dll**および GAC の Dll を登録します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-229">For your application to work with the most recent version of ODP.NET, install the **policy DLLs** and register the DLLs in the GAC.</span></span> <span data-ttu-id="ae10d-230">参照してください[.NET に関する FAQ の Oracle データ プロバイダー](http://www.oracle.com/technetwork/database/windows/faq-093106.html)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-230">See [Oracle Data Provider for .NET FAQ](http://www.oracle.com/technetwork/database/windows/faq-093106.html).</span></span>  
  
### <a name="sap-adapter"></a><span data-ttu-id="ae10d-231">SAP アダプター</span><span class="sxs-lookup"><span data-stu-id="ae10d-231">SAP adapter</span></span>  
  
-   <span data-ttu-id="ae10d-232">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] SAP システムは、Unicode または unicode 対応でないかどうかに関係なく、RFC SDK の Unicode バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-232">The [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] requires Unicode version of the RFC SDK irrespective of whether the SAP system is Unicode or non-Unicode.</span></span>  
  
-   <span data-ttu-id="ae10d-233">**必要なドライバー**: 次の表に、必要な Dll、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] SAP システムとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-233">**Required drivers**: The following table lists the DLLs required by the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to interface with the SAP system.</span></span> <span data-ttu-id="ae10d-234">これらの Dll を含むパッケージのほとんどは、SAP サービス Marketplace からダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-234">Most of the packages that contain these DLLs must be downloaded from the SAP Service Marketplace.</span></span> <span data-ttu-id="ae10d-235">SAP サービス Marketplace からダウンロードを取得します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-235">To get downloads from the SAP Service Marketplace:</span></span> 
  
    1.  <span data-ttu-id="ae10d-236">SAP サービス Marketplace から、ダウンロード マネージャーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-236">Install the Download Manager available from the SAP Service Marketplace.</span></span>  
  
    2.  <span data-ttu-id="ae10d-237">SAP サービス Marketplace 用の資格情報を使用して、ダウンロード マネージャーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-237">Configure the Download Manager by using your credentials for the SAP Service Marketplace.</span></span>  
  
    3.  <span data-ttu-id="ae10d-238">SAP のサービスの web サイトからソフトウェアをダウンロードする、組織内の SAP 管理者によって承認されます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-238">Be authorized by the SAP administrator in your organization to download software from the SAP service website.</span></span> <span data-ttu-id="ae10d-239">これは、機能は、' ソフトウェアのダウンロード ' 認証オブジェクトを SAP Software Distribution Center へのアクセスが制限されているため必要です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-239">This is required because access to the SAP Software Distribution Center is restricted by a 'Download Software' authorization object.</span></span> <span data-ttu-id="ae10d-240">これにより、ソフトウェアのダウンロードが承認されたユーザーのみであります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-240">This ensures that software is downloaded only by authorized users.</span></span>  
  
    4.  <span data-ttu-id="ae10d-241">SAP サービス Marketplace からダウンロードしたパッケージからファイルを抽出するために必要な最初に見つかったプログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-241">Install the SAPCAR program, which is required to extract the files from the packages that you download from the SAP Service Marketplace.</span></span> <span data-ttu-id="ae10d-242">最初に見つかったは SAP サービス マーケットプ レースからも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-242">SAPCAR is also available from the SAP Service Marketplace.</span></span>  
  
     <span data-ttu-id="ae10d-243">32 ビットおよび 64 ビット バージョンの[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、これらの各 32 ビットおよび 64 ビット バージョンは Dll である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-243">For the 32-bit and 64-bit version of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], you must have the respective 32-bit and 64-bit versions of these DLLs.</span></span>  
  
    -   <span data-ttu-id="ae10d-244">32 ビット コンピューターで C:\Windows\System32 フォルダーに、Dll の 32 ビット バージョンを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-244">On a 32-bit computer, the 32-bit version of the DLLs must be added to the C:\Windows\System32 folder.</span></span>  
  
    -   <span data-ttu-id="ae10d-245">64 ビット コンピューターで 32 ビット バージョンの Dll の C:\Windows\SysWow64 フォルダーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-245">On a 64-bit computer, the 32-bit version of the DLLs must be added to the C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="ae10d-246">Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-246">The 64-bit version of the DLLs must be added to the C:\Windows\System32 folder.</span></span>  
  
    |<span data-ttu-id="ae10d-247">SAP クライアント バージョン</span><span class="sxs-lookup"><span data-stu-id="ae10d-247">SAP client version</span></span>|<span data-ttu-id="ae10d-248">必要なドライバー</span><span class="sxs-lookup"><span data-stu-id="ae10d-248">Required drivers</span></span>|  
    |------------------------|----------------------|  
    |<span data-ttu-id="ae10d-249">6.4</span><span class="sxs-lookup"><span data-stu-id="ae10d-249">6.4</span></span>|<span data-ttu-id="ae10d-250">**BizTalk Adapter Pack 2013 のみ**</span><span class="sxs-lookup"><span data-stu-id="ae10d-250">**BizTalk Adapter Pack 2013 Only**</span></span><br /><br /> <span data-ttu-id="ae10d-251">- **SAP RFC SDK 6.40 UNICODE**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-251">- **SAP RFC SDK 6.40 UNICODE**.</span></span> <span data-ttu-id="ae10d-252">これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 です。SDK をダウンロードする手順は[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)です。ダウンロードして、SDK を展開したら、\rfcsdk\bin および \rfcsdk\lib フォルダーから、関連する場所に記載されている次の表の前のすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として**R3DLLINST.zip**です。これは、は、Microsoft ランタイム Dll を含んでおり、SAP サイトからダウンロードできます。SNOTE を参照してください<sup>* </sup> 684106 詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-252">This is available as part of SNOTE<sup>*</sup> 27517. The instructions to download the SDK are available at [http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691). After you have downloaded and extracted the SDK, copy all the DLLs from the \rfcsdk\bin and \rfcsdk\lib folders to the relevant location mentioned preceding this table.<br /><br /> - DLLs are available from SAP as part of **R3DLLINST.zip**. This contains Microsoft run-time DLLs and can be downloaded from the SAP site. See SNOTE<sup>*</sup> 684106 for more information.</span></span> <span data-ttu-id="ae10d-253">.Zip ファイルをダウンロードする[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-253">You can download the .zip file from [http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693).</span></span> <span data-ttu-id="ae10d-254">このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-254">This link has an “Attachments” option from where you can download the package.</span></span><br /><br /> <span data-ttu-id="ae10d-255">-SAP システムへの接続に SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-255">- If you use SAP Secure Network Communications (SNC) to connect to an SAP system, you must also have the relevant DLLs from SAP.</span></span> <span data-ttu-id="ae10d-256">これらの Dll は、32 ビットおよび 64 ビット プラットフォーム用に異なる、SNOTE で利用可能な<sup>* </sup> 352295 です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-256">These DLLs are different for 32-bit and 64-bit platforms and are available with SNOTE<sup>*</sup> 352295.</span></span> <span data-ttu-id="ae10d-257">Dll をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-257">You can download the DLLs from [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032).</span></span> <span data-ttu-id="ae10d-258">このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-258">This link has an “Attachments” option from where you can download the package.</span></span> <span data-ttu-id="ae10d-259">Dll の名前は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-259">The names of the DLLs are:</span></span><br /><br /> <span data-ttu-id="ae10d-260">- **32 ビット**: gsskrb5.dll、gssntlm.dll</span><span class="sxs-lookup"><span data-stu-id="ae10d-260">- **For 32-bit**: gsskrb5.dll, gssntlm.dll</span></span><br /><br /> <span data-ttu-id="ae10d-261">-  **64 ビット x86 用**: gx64krb5.dll、gx64ntlm.dll</span><span class="sxs-lookup"><span data-stu-id="ae10d-261">-  **For 64-bit x86**: gx64krb5.dll, gx64ntlm.dll</span></span>|  
    |<span data-ttu-id="ae10d-262">7.0</span><span class="sxs-lookup"><span data-stu-id="ae10d-262">7.0</span></span>|<span data-ttu-id="ae10d-263">- **SAP RFC SDK 7.00 UNICODE**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-263">- **SAP RFC SDK 7.00 UNICODE**.</span></span> <span data-ttu-id="ae10d-264">これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 です。SDK をダウンロードする手順は[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)です。ダウンロードし、SDK を抽出した後は、\rfcsdk\bin および \rfcsdk\lib フォルダーからと、関連する場所に記載されている次の表の前に、すべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として**R3DLLINST.zip**です。これは、は、Microsoft ランタイム Dll を含んでおり、SAP サイトからダウンロードできます。SNOTE を参照してください<sup>* </sup> 684106 詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-264">This is available as part of SNOTE<sup>*</sup> 27517. The instructions to download the SDK are available at [http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691). After you have downloaded and extracted the SDK, copy all the DLLs from the \rfcsdk\bin and \rfcsdk\lib folders and to the relevant location mentioned preceding this table.<br /><br /> - DLLs are available from SAP as part of **R3DLLINST.zip**. This contains Microsoft run-time DLLs and can be downloaded from the SAP site. See SNOTE<sup>*</sup> 684106 for more information.</span></span> <span data-ttu-id="ae10d-265">.Zip ファイルをダウンロードする[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-265">You can download the .zip file from [http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693).</span></span> <span data-ttu-id="ae10d-266">このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-266">This link has an “Attachments” option from where you can download the package.</span></span><br /><br /> <span data-ttu-id="ae10d-267">-SAP システムへの接続に SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-267">- If you use SAP Secure Network Communications (SNC) to connect to an SAP system, you must also have the relevant DLLs from SAP.</span></span> <span data-ttu-id="ae10d-268">これらの Dll は、32 ビットおよび 64 ビット プラットフォーム用に異なる、SNOTE で利用可能な<sup>* </sup> 352295 です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-268">These DLLs are different for 32-bit and 64-bit platforms and are available with SNOTE<sup>*</sup> 352295.</span></span> <span data-ttu-id="ae10d-269">Dll をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-269">You can download the DLLs from [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032).</span></span> <span data-ttu-id="ae10d-270">このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-270">This link has an “Attachments” option from where you can download the package.</span></span> <span data-ttu-id="ae10d-271">Dll の名前は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-271">The names of the DLLs are:</span></span><br /><br /> <span data-ttu-id="ae10d-272">- **32 ビット**: gsskrb5.dll、gssntlm.dll</span><span class="sxs-lookup"><span data-stu-id="ae10d-272">- **For 32-bit**: gsskrb5.dll, gssntlm.dll</span></span><br /><br /> <span data-ttu-id="ae10d-273">- **64 ビット x86 用**: gx64krb5.dll、gx64ntlm.dll</span><span class="sxs-lookup"><span data-stu-id="ae10d-273">- **For 64-bit x86**: gx64krb5.dll, gx64ntlm.dll</span></span>|  
    |<span data-ttu-id="ae10d-274">7.1</span><span class="sxs-lookup"><span data-stu-id="ae10d-274">7.1</span></span>|<span data-ttu-id="ae10d-275">- **SAP RFC SDK 7.10 UNICODE**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-275">- **SAP RFC SDK 7.10 UNICODE**.</span></span> <span data-ttu-id="ae10d-276">これは、使用可能な SNOTE の一部として<sup>* </sup> 27517 です。SDK をダウンロードする手順は[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)です。ダウンロードして、SDK を展開したら、\rfcsdk\bin および \rfcsdk\lib フォルダーから、関連する場所に記載されている次の表の前のすべての Dll をコピーします。<br /> <br /> -Dll には SAP からの一部として**R3DLLINST.zip**です。これは、は、Microsoft ランタイム Dll を含んでおり、SAP サイトからダウンロードできます。SNOTE を参照してください<sup>* </sup> 684106 詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-276">This is available as part of SNOTE<sup>*</sup> 27517. The instructions to download the SDK are available at [http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691). After you have downloaded and extracted the SDK, copy all the DLLs from the \rfcsdk\bin and \rfcsdk\lib folders to the relevant location mentioned preceding this table.<br /><br /> - DLLs are available from SAP as part of **R3DLLINST.zip**. This contains Microsoft run-time DLLs and can be downloaded from the SAP site. See SNOTE<sup>*</sup> 684106 for more information.</span></span> <span data-ttu-id="ae10d-277">.Zip ファイルをダウンロードする[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-277">You can download the .zip file from [http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693).</span></span> <span data-ttu-id="ae10d-278">このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-278">This link has an “Attachments” option from where you can download the package.</span></span><br /><br /> <span data-ttu-id="ae10d-279">Microsoft Visual C ランタイム Dll SAP 7.1 クライアントに必要なには、次のリンクからです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-279">- Microsoft Visual C++ run-time DLLs required for SAP 7.1 client are available from the following links:</span></span><br /><br /> <span data-ttu-id="ae10d-280">- **32 ビット SAP 7.1 クライアントを**: から Vcredist_x86.exe [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-280">- **For 32-bit SAP 7.1 client**:  Vcredist_x86.exe from [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086).</span></span><br /><br /> <span data-ttu-id="ae10d-281">-                                 **64 ビット SAP 7.1 クライアントを**: から Vcredist_x64.exe [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-281">-                                 **For 64-bit SAP 7.1 client**: Vcredist_x64.exe from [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087).</span></span><br /><br /> <span data-ttu-id="ae10d-282">-SAP システムへの接続に SAP セキュリティで保護されたネットワーク通信 (SNC) を使用する場合は、SAP から関連する Dll を必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-282">- If you use SAP Secure Network Communications (SNC) to connect to an SAP system, you must also have the relevant DLLs from SAP.</span></span> <span data-ttu-id="ae10d-283">これらの Dll は、32 ビットおよび 64 ビット プラットフォーム用に異なる、SNOTE で利用可能な<sup>* </sup> 352295 です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-283">These DLLs are different for 32-bit and 64-bit platforms and are available with SNOTE<sup>*</sup> 352295.</span></span> <span data-ttu-id="ae10d-284">Dll をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-284">You can download the DLLs from [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032).</span></span> <span data-ttu-id="ae10d-285">このリンクには、"Attachments"からパッケージをダウンロードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-285">This link has an “Attachments” option from where you can download the package.</span></span> <span data-ttu-id="ae10d-286">Dll の名前は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-286">The names of the DLLs are:</span></span><br /><br /> <span data-ttu-id="ae10d-287">- **32 ビット**: gsskrb5.dll、gssntlm.dll</span><span class="sxs-lookup"><span data-stu-id="ae10d-287">- **For 32-bit**: gsskrb5.dll, gssntlm.dll</span></span><br /><br /> <span data-ttu-id="ae10d-288">- **64 ビット x86 用**: gx64krb5.dll、gx64ntlm.dll</span><span class="sxs-lookup"><span data-stu-id="ae10d-288">- **For 64-bit x86**: gx64krb5.dll, gx64ntlm.dll</span></span>|  
  
     * <span data-ttu-id="ae10d-289">SNOTEs は、SAP でリリースされた修正プログラムに付属のリリース ノートです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-289">SNOTEs are release notes that accompany fixes released by SAP.</span></span>  

### <a name="siebel-adapter"></a><span data-ttu-id="ae10d-290">Siebel アダプター</span><span class="sxs-lookup"><span data-stu-id="ae10d-290">Siebel adapter</span></span>  
<span data-ttu-id="ae10d-291">余分な手順はありません。</span><span class="sxs-lookup"><span data-stu-id="ae10d-291">No extra steps.</span></span>
  
### <a name="sql-adapter"></a><span data-ttu-id="ae10d-292">SQL アダプター</span><span class="sxs-lookup"><span data-stu-id="ae10d-292">SQL adapter</span></span>  
  
<span data-ttu-id="ae10d-293">**必要なドライバー**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-293">**Required drivers**:</span></span>  
  
-   <span data-ttu-id="ae10d-294">**SQL Server 2005 の**: SQL Server でユーザー定義型 (Udt) を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae10d-294">**For SQL Server 2005**: If you create User Defined Types (UDTs) in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
-   <span data-ttu-id="ae10d-295">**SQL Server 2014、SQL Server 2012、SQL Server 2008 R2、SQL Server 2008 SP1 の**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-295">**For SQL Server 2014, SQL Server 2012, SQL Server 2008 R2,SQL Server 2008 SP1**:</span></span>  
  
    -   <span data-ttu-id="ae10d-296">SQL Server のバージョン、たとえば、Geography に付属して Udt を使用する場合は、次の Dll は、SQL Server 上の操作を実行するアダプターを使用するコンピューター上に存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-296">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="ae10d-297">など、SQL Server 上の操作を実行する BizTalk プロジェクトを作成する場合は、これらの Dll が BizTalk Server が実行されているコンピューター上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-297">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="ae10d-298">Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-298">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="ae10d-299">SqlServerSpatial.dll が System32 フォルダーにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae10d-299">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>    
        
        <span data-ttu-id="ae10d-300">SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-300">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>          
  
    -   <span data-ttu-id="ae10d-301">FILESTREAM データ型の列に対して操作を実行するアダプターを使用する場合は、SQL クライアント接続 SDK がインストールされている必要があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae10d-301">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="ae10d-302">SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-302">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="ae10d-303">アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-303">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  

    -   <span data-ttu-id="ae10d-304">SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-304">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>

## <a name="64-bit-support"></a><span data-ttu-id="ae10d-305">64 ビットのサポート</span><span class="sxs-lookup"><span data-stu-id="ae10d-305">64-bit support</span></span>

<span data-ttu-id="ae10d-306">Siebel アダプターは、32 ビット ホスト インスタンスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ae10d-306">The Siebel adapter is supported in a 32-bit host instance.</span></span> <span data-ttu-id="ae10d-307">Siebel アダプターを 64 ビット ホスト インスタンスで実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae10d-307">It is not supported to run the Siebel adapter in a 64-bit host instance.</span></span> 

<span data-ttu-id="ae10d-308">他のすべてのアダプターは、32 ビットまたは 64 ビット ホスト インスタンスで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-308">All the other adapters can run in a 32-bit or 64-bit host instance.</span></span> 


  
 <span data-ttu-id="ae10d-309">32 ビットおよび 64 ビットのインストールのサポートされているインストール シナリオの詳細については[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を参照してください[32 ビットおよび 64 ビット プラットフォームでは、BizTalk Adapter Pack のインストール シナリオ](#BKMK_Install_Scenarios)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-309">For more information about the supported installation scenarios for installing the 32-bit and 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], see [Scenarios for Installing the BizTalk Adapter Pack on 32-bit and 64-bit Platforms](#BKMK_Install_Scenarios).</span></span>  
  
<a name="BKMK_Install_Adap"></a>   
## <a name="installing-the-biztalk-adapter-pack"></a><span data-ttu-id="ae10d-310">BizTalk Adapter Pack をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-310">Installing the BizTalk Adapter Pack</span></span>  
 <span data-ttu-id="ae10d-311">すべてを確認して、[ソフトウェアの前提条件](#BKMK_Prereqs)がインストールする前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-311">Make sure all the [software prerequisites](#BKMK_Prereqs) are installed before installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ae10d-312">インストールすることができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="ae10d-312">You can install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="ae10d-313">**対話モードで**: セットアップ ウィザードを実行</span><span class="sxs-lookup"><span data-stu-id="ae10d-313">**In interactive mode**: Run the setup wizard</span></span>  
  
-   <span data-ttu-id="ae10d-314">**サイレント モードで**: コマンドラインを使用して</span><span class="sxs-lookup"><span data-stu-id="ae10d-314">**In silent mode**: Use the command line</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ae10d-315">インストールするコンピューターで管理者特権を持つ必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ウィザードまたはコマンドラインを使用してをインストールするかどうかのあるかにかかわらず、します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-315">You must have administrative privileges on the computer where you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], irrespective of whether you are installing using the wizard or the command line.</span></span>  

### <a name="typical-vs-custom-installation"></a><span data-ttu-id="ae10d-316">標準セットアップとカスタム インストール</span><span class="sxs-lookup"><span data-stu-id="ae10d-316">Typical vs custom installation</span></span>  
<span data-ttu-id="ae10d-317">このセクションには、インストールの種類と各オプションでインストールされている機能が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-317">This section lists the installation types, and the features that are installed with each option:</span></span>  
  
-   <span data-ttu-id="ae10d-318">**標準**と**完了**オプションは、関連付けられているデータ プロバイダーとすべてのアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-318">The **Typical** and **Complete** options install all the adapters, with the associated data providers.</span></span> <span data-ttu-id="ae10d-319">インストールする特定のアダプターを選択するオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="ae10d-319">You do not have the option of choosing a specific adapter to install.</span></span>  
  
-   <span data-ttu-id="ae10d-320">**カスタム**オプションは、関連付けられているデータ プロバイダーと 1 つまたは複数のアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-320">The **Custom** option installs one or more adapters, with the associated data providers.</span></span> <span data-ttu-id="ae10d-321">インストールするには、どのアダプターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-321">You can choose which adapters to install.</span></span> <span data-ttu-id="ae10d-322">データ プロバイダーをインストールする場合は、また、対応するアダプターをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-322">If you choose to install a data provider, you must also install the corresponding adapter.</span></span> <span data-ttu-id="ae10d-323">ただし、対応するデータ プロバイダーをインストールしなくても、アダプターをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-323">However, you can install an adapter without installing the corresponding data provider.</span></span> <span data-ttu-id="ae10d-324">これには、展開、 **ADO プロバイダー**ノード、およびインストールしたくないプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-324">Do this by expanding the **ADO Providers** node, and then selecting the providers that you don't want to install.</span></span> <span data-ttu-id="ae10d-325">参照してください[対話モードで BizTalk Adapter をインストールするパック](#BKMK_Install_wizard)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-325">See [Installing the BizTalk Adapter Pack in Interactive Mode](#BKMK_Install_wizard).</span></span>  
  
     <span data-ttu-id="ae10d-326">たとえば、インストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]もインストールする必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-326">For example, if you install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], you must also install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="ae10d-327">ただし、インストールすることができます、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]インストールしなくても、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-327">However, you can install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] without installing the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-32-bit-and-64-bit-platforms"></a><span data-ttu-id="ae10d-328">32 ビットおよび 64 ビット プラットフォームでは、BizTalk Adapter Pack をインストールするためのシナリオ</span><span class="sxs-lookup"><span data-stu-id="ae10d-328">Scenarios for installing the BizTalk Adapter Pack on 32-bit and 64-bit platforms</span></span>  
 <span data-ttu-id="ae10d-329">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-329">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] can be used for:</span></span> 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="ae10d-330">デザイン時 (場合、LOB アプリケーションでの操作のメタデータの生成)</span><span class="sxs-lookup"><span data-stu-id="ae10d-330"> design time (when generating metadata for operations on LOB applications)</span></span>
  
-   <span data-ttu-id="ae10d-331">BizTalk Server 管理コンソール デザイン時 (物理ポートの作成)</span><span class="sxs-lookup"><span data-stu-id="ae10d-331">BizTalk Server Administration console design time (for creating physical ports)</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-332">BizTalk Server 管理コンソールは、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-332">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="ae10d-333">BizTalk ランタイム (ときに送信し、LOB アプリケーションからメッセージを受信)</span><span class="sxs-lookup"><span data-stu-id="ae10d-333">BizTalk run time (when sending and receiving messages from LOB applications)</span></span>

<span data-ttu-id="ae10d-334">これらすべての検索の 1 台のコンピューターを使用したり、別のコンピューターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-334">You can use a single computer for all these taks, or use different computers.</span></span> <span data-ttu-id="ae10d-335">両方[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]と BizTalk MMC は 32 ビット プロセスが、32 ビットをインストールする必要があります[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]デザイン時のタスクを完了するコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-335">Because both [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on the computer where you complete the design-time tasks.</span></span> 

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-32-bit-platform"></a><span data-ttu-id="ae10d-336">32 ビット プラットフォーム上で、BizTalk Adapter Pack をインストールするためのシナリオ</span><span class="sxs-lookup"><span data-stu-id="ae10d-336">Scenarios for installing the BizTalk Adapter Pack on a 32-bit platform</span></span>  
 <span data-ttu-id="ae10d-337">32 ビット プラットフォームでサポートされるシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-337">The supported scenarios on a 32-bit platform include:</span></span>  
  
|<span data-ttu-id="ae10d-338">Visual Studio のデザイン時の</span><span class="sxs-lookup"><span data-stu-id="ae10d-338">For Visual Studio design time</span></span>|<span data-ttu-id="ae10d-339">MMC の BizTalk のデザイン時</span><span class="sxs-lookup"><span data-stu-id="ae10d-339">For BizTalk MMC design time</span></span>|<span data-ttu-id="ae10d-340">Biztalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="ae10d-340">For BizTalk run time</span></span>|<span data-ttu-id="ae10d-341">Visual Studio のデザイン時およびデザイン時の BizTalk MMC + BizTalk 実行時間</span><span class="sxs-lookup"><span data-stu-id="ae10d-341">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="ae10d-342">がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-342">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-343">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-343">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-344">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-344">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="ae10d-345">がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-345">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-346">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-346">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-347">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-347">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="ae10d-348">がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-348">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-349">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-349">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-350">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-350">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="ae10d-351">がインストール 32 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-351">- Install 32-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-352">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-352">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-353">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-353">- Install 32-bit LOB client and other required DLLs.</span></span>|  
  
#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-64-bit-platform"></a><span data-ttu-id="ae10d-354">64 ビット プラットフォーム上で、BizTalk Adapter Pack をインストールするためのシナリオ</span><span class="sxs-lookup"><span data-stu-id="ae10d-354">Scenarios for installing the BizTalk Adapter Pack on a 64-bit platform</span></span>  
 <span data-ttu-id="ae10d-355">64 ビット プラットフォームでサポートされるシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-355">The supported scenarios on a 64-bit platform include:</span></span>  
  
|<span data-ttu-id="ae10d-356">Visual Studio のデザイン時の</span><span class="sxs-lookup"><span data-stu-id="ae10d-356">For Visual Studio design time</span></span>|<span data-ttu-id="ae10d-357">MMC の BizTalk のデザイン時</span><span class="sxs-lookup"><span data-stu-id="ae10d-357">For BizTalk MMC design time</span></span>|<span data-ttu-id="ae10d-358">Biztalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="ae10d-358">For BizTalk run time</span></span>|<span data-ttu-id="ae10d-359">Visual Studio のデザイン時およびデザイン時の BizTalk MMC + BizTalk 実行時間</span><span class="sxs-lookup"><span data-stu-id="ae10d-359">For Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="ae10d-360">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-360">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-361">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-361">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-362">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-362">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="ae10d-363">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-363">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-364">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-364">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-365">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-365">- Install 32-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="ae10d-366">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-366">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ae10d-367">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-367">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-368">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-368">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-369">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-369">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ae10d-370">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-370">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ae10d-371">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-371">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-372">がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-372">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-373">-64 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-373">- Install 64-bit LOB client and other required DLLs.</span></span>|<span data-ttu-id="ae10d-374">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-374">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ae10d-375">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-375">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-376">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-376">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-377">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-377">- Install 32-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ae10d-378">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-378">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ae10d-379">がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-379">- Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-380">がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-380">- Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-381">-64 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-381">- Install 64-bit LOB client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ae10d-382">がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-382">- Install 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="ae10d-383">32 ビット LOB クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-383">- Install 32-bit LOB client and other required DLLs.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ae10d-384">デザイン時のタスクを実行する任意のコンピューターでいずれかの操作を使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-384">On any computer where you want to do design-time tasks, using either [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-interactive-mode"></a><span data-ttu-id="ae10d-385">対話モードで BizTalk Adapter Pack をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-385">Installing the BizTalk Adapter Pack in interactive mode</span></span>  
<span data-ttu-id="ae10d-386">次の手順に従って、インストールを完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-386">Complete the following steps to install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the setup wizard.</span></span>  
  
1.  <span data-ttu-id="ae10d-387">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール メディアで、実行**Setup.exe**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-387">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation media, run **Setup.exe**.</span></span>  
  
2.  <span data-ttu-id="ae10d-388">選択**Microsoft BizTalk Adapters インストール**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-388">Select **Install Microsoft BizTalk Adapters**.</span></span> <span data-ttu-id="ae10d-389">次のウィンドウで次のように選択します。 **Microsoft BizTalk Adapter Pack のインストール**または**インストール Microsoft BizTalk Adapter Pack (x64)**プラットフォームに応じて、します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-389">In the next window, select **Install Microsoft BizTalk Adapter Pack** or **Install Microsoft BizTalk Adapter Pack (x64)**, depending on your platform.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-390">インストールする場合、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]バーチャル マシンで、セットアップ ウィザードは使用可能なディスク容量については、セットアップがチェックされることを通知 ダイアログ ボックス続行されません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-390">If you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="ae10d-391">このような場合、サイレント インストール オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-391">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="ae10d-392">参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ae10d-392">See [Installing the BizTalk Adapter Pack in Silent Mode](#BKMK_SilentInst) (in this topic).</span></span>  
  
3.  <span data-ttu-id="ae10d-393">[ようこそ] 画面で、次のように選択します。**次**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-393">On the Welcome screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="ae10d-394">使用許諾契約書 (EULA) に同意し、**次**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-394">Accept the end-user license agreement (EULA), and then select **Next**.</span></span>  
  
5.  <span data-ttu-id="ae10d-395">**セットアップの種類を選択して**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-395">In **Choose Setup Type**:</span></span>  
  
    -   <span data-ttu-id="ae10d-396">最も一般的な機能をインストールする選択**標準**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-396">To install the most common features, select **Typical**.</span></span>  
  
    -   <span data-ttu-id="ae10d-397">インストールするアダプターを選択するには、次のように選択します。**カスタム**、し、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-397">To select the adapters you want to install, select **Custom**, and then proceed to the next step.</span></span>  
  
    -   <span data-ttu-id="ae10d-398">すべての機能をインストールする選択**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-398">To install all the features, select **Complete**.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="ae10d-399">エンタープライズ アプリケーションとのインターフェイスで、選択に使用するアダプターのみをインストールする、**カスタム**インストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-399">To install only the adapter that you use to interface with your enterprise application, select the **Custom** installation.</span></span>  
  
6. <span data-ttu-id="ae10d-400">**必要な**カスタム インストールを選択した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-400">**Required** only if you chose the Custom installation.</span></span> <span data-ttu-id="ae10d-401">選択した場合、**標準**または**完了**インストールし、この手順をスキップし、手順 7. に進みます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-401">If you chose the **Typical** or **Complete** installation, then skip this step, and go to step 7.</span></span>  
  
    1.  <span data-ttu-id="ae10d-402">**カスタム セットアップ**、展開**ベース アダプター**に利用可能なアダプターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae10d-402">In **Custom Setup**, expand **Base Adapters** to see the available adapters.</span></span>  
  
    2.  <span data-ttu-id="ae10d-403">必要のないアダプターの場合、アダプターの横にあるアイコンを選択し、**全体の機能は使用できません**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-403">For the adapters that you don't want, select the icon next to the adapter, and then select **Entire feature will be unavailable**.</span></span>  
  
    3.  <span data-ttu-id="ae10d-404">展開**ADO プロバイダー**、しをインストールしたくないプロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-404">Expand **ADO Providers**, and then select the providers that you don't want to install.</span></span>  
  
    4.  <span data-ttu-id="ae10d-405">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-405">Select **Next**.</span></span>  
  
7.  <span data-ttu-id="ae10d-406">**[インストール]**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-406">Select **Install**.</span></span>  
  
8.  <span data-ttu-id="ae10d-407">**カスタマー エクスペリエンス向上プログラム**、登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-407">In **Customer Experience Improvement Program**, you can choose to enroll.</span></span> <span data-ttu-id="ae10d-408">登録する場合は、Microsoft と、次のデータを共有できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-408">If you enroll, you can share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="ae10d-409">インストールしているコンピューターのハードウェアに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-409">Data related to the computer hardware on which you are installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="ae10d-410">使用するエンタープライズ アプリケーションのバージョンに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-410">Data related to the enterprise application versions you are using with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
     <span data-ttu-id="ae10d-411">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-411">Select **OK**.</span></span> <span data-ttu-id="ae10d-412">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-412">[CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) provides more information.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-413">修復モードで、セットアップを実行して、この設定を変更することが常に**プログラム**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-413">You can always change this setting by running the Setup in Repair mode from **Programs**.</span></span>  
  
9. <span data-ttu-id="ae10d-414">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-414">Select **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-silent-mode"></a><span data-ttu-id="ae10d-415">サイレント モードで BizTalk Adapter Pack をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-415">Installing the BizTalk Adapter Pack in silent mode</span></span>  
 <span data-ttu-id="ae10d-416">使用して、 **msiexec**サイレント インストールを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="ae10d-416">Use the **msiexec** command to do a silent installation.</span></span> <span data-ttu-id="ae10d-417">Msiexec コマンドの一部としてインストールする個々 のコンポーネントを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-417">As part of the msiexec command, enter the individual components that you want to install.</span></span> <span data-ttu-id="ae10d-418">次の表に、内の各コンポーネントの値、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-418">The following table lists the values for each component in the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ae10d-419">特定のコンポーネントをインストール (または削除) するのにには、これらの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-419">Use these values to install (or remove) specific components.</span></span> <span data-ttu-id="ae10d-420">ホスト インスタンスをインストール (または削除) するには、複数のコンポーネントは、コンマ区切りでこれらの値の組み合わせを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-420">To install (or remove) more than one component, you can use a combination of these values separated by a comma.</span></span>  
  
|<span data-ttu-id="ae10d-421">コンポーネント名</span><span class="sxs-lookup"><span data-stu-id="ae10d-421">Component name</span></span>|<span data-ttu-id="ae10d-422">コマンド ライン プロパティの対応する値</span><span class="sxs-lookup"><span data-stu-id="ae10d-422">Corresponding value for command-line properties</span></span>|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="ae10d-423">DbFeature</span><span class="sxs-lookup"><span data-stu-id="ae10d-423">DbFeature</span></span>|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="ae10d-424">OracleEBSFeature</span><span class="sxs-lookup"><span data-stu-id="ae10d-424">OracleEBSFeature</span></span>|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="ae10d-425">SapBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="ae10d-425">SapBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="ae10d-426">SiebelBaseAdapterFeature</span><span class="sxs-lookup"><span data-stu-id="ae10d-426">SiebelBaseAdapterFeature</span></span>|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="ae10d-427">SqlFeature</span><span class="sxs-lookup"><span data-stu-id="ae10d-427">SqlFeature</span></span>|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="ae10d-428">SapAdoFeature</span><span class="sxs-lookup"><span data-stu-id="ae10d-428">SapAdoFeature</span></span><br /><br /> <span data-ttu-id="ae10d-429">**注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]もします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-429">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] also.</span></span>|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="ae10d-430">SiebelAdoFeature</span><span class="sxs-lookup"><span data-stu-id="ae10d-430">SiebelAdoFeature</span></span><br /><br /> <span data-ttu-id="ae10d-431">**注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]もします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-431">**Note**: You must provide this value only if you are installing the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] also.</span></span>|  
|<span data-ttu-id="ae10d-432">すべてのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="ae10d-432">All components</span></span>|<span data-ttu-id="ae10d-433">ALL</span><span class="sxs-lookup"><span data-stu-id="ae10d-433">ALL</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae10d-434">機能名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-434">The feature names are case-sensitive.</span></span>  
  
 <span data-ttu-id="ae10d-435">次の手順は、のサイレント インストールを完了する方法を示します[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]さまざまなコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-435">The following steps show you how to complete a silent installation of [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] for different components.</span></span>  
  
##### <a name="install-in-silent-mode"></a><span data-ttu-id="ae10d-436">サイレント モードでインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-436">Install in silent mode</span></span>  
  
1.  <span data-ttu-id="ae10d-437">コマンド プロンプトを開きに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]でルート、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-437">Open a command prompt, and go to the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] root in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span>  
  
2.  <span data-ttu-id="ae10d-438">インストールする内容に基づいて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-438">Run the following commands based on what you want to install:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-439">X64 ベースのプラットフォームでのサイレント インストールには、置換`AdaptersSetup.msi`で`AdaptersSetup64.msi`次のコマンドにします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-439">To do silent installation on an x64-based platform, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi` in the following commands.</span></span>  
  
    -   <span data-ttu-id="ae10d-440">アダプターは、.NET Framework データ プロバイダーを含む、すべてをインストールする完全なインストールを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-440">To perform a complete installation, which installs all the adapters including the .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   <span data-ttu-id="ae10d-441">のみをインストールする、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="ae10d-441">To install only the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-442">のみをインストールする、[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="ae10d-442">To install only the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-443">のみをインストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="ae10d-443">To install only the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-444">インストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]と共に[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="ae10d-444">To install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] along with [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-445">のみをインストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="ae10d-445">To install only the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-446">インストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]と共に[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="ae10d-446">To install the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] along with [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-447">のみをインストールする、[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]種類。</span><span class="sxs-lookup"><span data-stu-id="ae10d-447">To install only the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-448">すべてのベース アダプターをインストールするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-448">To install all the base adapters, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-449">2 つの .NET Framework データ プロバイダーをインストールするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-449">To install the two .NET Framework Data Providers, type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-450">コンマで区切って、コンポーネントでカスタム インストールのすべての型。</span><span class="sxs-lookup"><span data-stu-id="ae10d-450">Any type of custom installation by separating the components by a comma.</span></span> <span data-ttu-id="ae10d-451">たとえば、インストールするため、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]で、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、および[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]型。</span><span class="sxs-lookup"><span data-stu-id="ae10d-451">For example, to install the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] with the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], and the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   <span data-ttu-id="ae10d-452">CEIP をサイレント インストールの一部として登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-452">You can also opt to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="ae10d-453">型:</span><span class="sxs-lookup"><span data-stu-id="ae10d-453">Type:</span></span>  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         <span data-ttu-id="ae10d-454">既定では、オプションは false です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-454">By default the option is false.</span></span> 
  
        > [!IMPORTANT]
        >  <span data-ttu-id="ae10d-455">インストール中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでの評価版、CEIP の既定のオプションが true です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-455">While installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] Evaluation version in silent mode, the default option for CEIP is true.</span></span>  
  
     <span data-ttu-id="ae10d-456">Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-456">For more information about the msiexec command type `msiexec` on the command line and press `ENTER`.</span></span> <span data-ttu-id="ae10d-457">移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-457">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
<a name="BKMK_PostInst"></a>   
### <a name="after-installing-the-biztalk-adapter-pack"></a><span data-ttu-id="ae10d-458">BizTalk Adapter Pack をインストールした後</span><span class="sxs-lookup"><span data-stu-id="ae10d-458">After installing the BizTalk Adapter Pack</span></span>  
 <span data-ttu-id="ae10d-459">インストールした後、次のタスクを実行する必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]と、各アダプターを実行する操作に基づきます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-459">You may need to do the following tasks after installing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], based on what operations you want to do with each adapter:</span></span>  
  
-   <span data-ttu-id="ae10d-460">[新しい Oracle.DataAccess.dll バージョンを使用する Oracle データベース アダプター構成](#BKMK_ConfigNewOracleDLL)OracleDB 構成ファイルにします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-460">[Configure the Oracle Database adapter to use a newer Oracle.DataAccess.dll version](#BKMK_ConfigNewOracleDLL) in the OracleDB configuration file.</span></span>  
  
-   <span data-ttu-id="ae10d-461">[SQL Server データベース オブジェクトを作成する (SAP アダプター) の場合のみ](#BKMK_CreateSQLServer)を SAP システムでトランザクションの Rfc (tRFCs) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-461">[Create SQL Server Database Objects (Only for the SAP Adapter)](#BKMK_CreateSQLServer) to invoke transactional RFCs (tRFCs) in an SAP system.</span></span>  
  
-   <span data-ttu-id="ae10d-462">[アダプターのバインドを登録](#BKMK_Register_Bindings)とそのためには、セットアップ ウィザードが失敗した場合に、.NET Framework データ プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="ae10d-462">[Register the adapter bindings](#BKMK_Register_Bindings) and the .NET Framework Data Providers if the setup wizard fails to do so.</span></span>  
  
-   <span data-ttu-id="ae10d-463">[公開キーとバージョン特定](#BKMK_PubKey)異なるアダプター ファイルのです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-463">[Determine the Public Key and Version](#BKMK_PubKey) of the different adapter files.</span></span>  
  
-   <span data-ttu-id="ae10d-464">[インストールのカスタム Rfc](#BKMK_InstallCustomRFC)をインストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-464">[Install the Custom RFCs](#BKMK_InstallCustomRFC) if you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span>  
  
<a name="BKMK_ConfigNewOracleDLL"></a>   
#### <a name="configure-the-oracle-database-adapter-to-use-a-newer-oracledataaccessdll-version"></a><span data-ttu-id="ae10d-465">新しい Oracle.DataAccess.dll バージョンを使用する Oracle データベース アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-465">Configure the Oracle Database adapter to use a newer Oracle.DataAccess.dll version</span></span>  
 <span data-ttu-id="ae10d-466">Wcf-oracledb アダプターを使用または生成されたアダプターを使用する Visual Studio を使用するためのポートを構成するときに、アダプターが Oracle.DataAccess.dll バージョン 2.111.7.0 必要があること、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-466">When you configure a port to use the WCF-OracleDB adapter or use Visual Studio to consume a generated adapter, a message displays that the adapter needs Oracle.DataAccess.dll version 2.111.7.0.</span></span> <span data-ttu-id="ae10d-467">このメッセージを解決するには、サポートされている Oracle.DataAccess.dll バージョンをインストール (を参照してください[バージョンのリストをサポート](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))、し、更新、 `bindingRedirect` OracleDB 構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="ae10d-467">To resolve this message, install a supported Oracle.DataAccess.dll version (see [supported version list](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)), and then update the `bindingRedirect` element in the OracleDB configuration file.</span></span> <span data-ttu-id="ae10d-468">手順:</span><span class="sxs-lookup"><span data-stu-id="ae10d-468">Steps:</span></span>  
  
1.  <span data-ttu-id="ae10d-469">BizTalk Server では、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-469">On the BizTalk Server, go to the following folders:</span></span>  
  
     <span data-ttu-id="ae10d-470">*ドライブ*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin</span><span class="sxs-lookup"><span data-stu-id="ae10d-470">*drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin</span></span>  
  
     <span data-ttu-id="ae10d-471">*ドライブ*: \Program Files (x86) \Microsoft BizTalk Adapter Pack\bin</span><span class="sxs-lookup"><span data-stu-id="ae10d-471">*drive*:\Program Files (x86)\Microsoft BizTalk Adapter Pack\bin</span></span>  
  
2.  <span data-ttu-id="ae10d-472">Microsoft.Adapters.OracleDB.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-472">Open the Microsoft.Adapters.OracleDB.config file.</span></span>  
  
3.  <span data-ttu-id="ae10d-473">次のセクションを見つけて次コピー/貼り付け。</span><span class="sxs-lookup"><span data-stu-id="ae10d-473">Find the following section, and copy/paste the following:</span></span>  
  
    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  
  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-474">この例では設定*newVersion* 2.112.1.00 にします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-474">In this example, we set *newVersion* to 2.112.1.00.</span></span> <span data-ttu-id="ae10d-475">この値をインストールしたバージョンに設定します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-475">Set this value to the version you have installed.</span></span>  
  
> [!IMPORTANT]
>  -   <span data-ttu-id="ae10d-476">このグループに複数の BizTalk Server がある場合は、グループ内のすべての BizTalk サーバーでこの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="ae10d-476">If there are multiple BizTalk Servers in this group, make this change on all the BizTalk servers in the group.</span></span>  
> -   <span data-ttu-id="ae10d-477">*NewVersion* Oracle.DataAccess.dll ファイルをコンピューターにインストールされているのバージョンに基づく更新する値が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-477">The *newVersion* value needs to be updated based on the version of the Oracle.DataAccess.dll file installed on the computer.</span></span>  <span data-ttu-id="ae10d-478">Oracle.DataAccess.dll は、Oracle からインストールする Oracle クライアントに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae10d-478">Oracle.DataAccess.dll is included with the Oracle Client you install from Oracle.</span></span>  <span data-ttu-id="ae10d-479">される Oracle クライアント バージョンをインストールする必要がありますのみ[BizTalk Adapter Pack でサポートされている](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-479">You must only install an Oracle Client version that is [supported by the BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).</span></span>  
  
<a name="BKMK_CreateSQLServer"></a>   
#### <a name="create-sql-server-database-objects-only-for-the-sap-adapter"></a><span data-ttu-id="ae10d-480">(SAP アダプター) の場合のみ SQL Server データベース オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-480">Create SQL Server Database objects (only for the SAP adapter)</span></span>  
 <span data-ttu-id="ae10d-481">SAP システムで tRFCs を呼び出し、実行、 *SapAdapter DbScript-Install.sql* SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="ae10d-481">To invoke tRFCs in an SAP system, run the *SapAdapter-DbScript-Install.sql* SQL script.</span></span> <span data-ttu-id="ae10d-482">このスクリプトがインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールし、SQL Server でデータベース オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-482">This script is installed with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, and creates database objects in SQL Server.</span></span> <span data-ttu-id="ae10d-483">インストールされている通常の\<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-483">The script is typically installed at \<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ae10d-484">TRFCs を呼び出すため、アダプターを使用しているときにそのデータベース名を入力する限り、任意の SQL Server データベースに対してこのスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-484">You can run this script against any SQL Server database, as long as you enter that database name while using the adapter to invoke tRFCs.</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-adapter-bindings"></a><span data-ttu-id="ae10d-485">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-485">Register the adapter bindings</span></span>  
 <span data-ttu-id="ae10d-486">中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、セットアップ ウィザードがアダプターのバインドが、または、.NET Framework Data Provider for mySAP Business Suite を登録に失敗する可能性がありますが、アダプターのインストールがセットアップが続行されます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-486">During the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, the setup wizard may fail to register the adapter bindings or the .NET Framework Data Provider for mySAP Business Suite, but setup proceeds with the adapter installation.</span></span> <span data-ttu-id="ae10d-487">Windows Communication Foundation (WCF) のインストールに問題があります[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-487">This might result due to problems with Windows Communication Foundation (WCF) installation, [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span>  
  
<span data-ttu-id="ae10d-488">次の手順を完了*のみ*machine.config ファイルに、アダプターのバインドまたは .NET Framework データ プロバイダーを登録するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="ae10d-488">Complete these steps *only* if the setup wizard fails to register the adapter bindings or .NET Framework Data Providers in the machine.config file.</span></span>  
  
###### <a name="register-the-adapter-bindings-or-the-net-framework-data-providers"></a><span data-ttu-id="ae10d-489">アダプターのバインドまたは .NET Framework データ プロバイダーを登録します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-489">Register the adapter bindings or the .NET Framework data providers</span></span>  
  
1.  <span data-ttu-id="ae10d-490">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-490">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="ae10d-491">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-491">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
2.  <span data-ttu-id="ae10d-492">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-492">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="ae10d-493">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-493">Register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="ae10d-494">検索、`system.serviceModel`要素、およびその下にある次の追加。</span><span class="sxs-lookup"><span data-stu-id="ae10d-494">Search for the `system.serviceModel` element, and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="ae10d-495">検索、 `bindingElementExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="ae10d-495">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="ae10d-496">不足しているアダプターのバインドを探します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-496">Look for the missing adapter binding.</span></span> <span data-ttu-id="ae10d-497">次のセクションを追加、`bindingElementExtensions`バインドに応じて、不足しているアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-497">Add the following sections under the `bindingElementExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="ae10d-498">セットアップ ウィザードに任意登録に失敗した場合、すべてのバインドを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-498">You must register all the bindings if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="ae10d-499">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-499">For the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-500">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-500">For the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-501">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-501">For the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-502">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-502">For the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-503">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-503">For the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="ae10d-504">検索、 `bindingExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="ae10d-504">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="ae10d-505">不足しているアダプターのバインドを探します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-505">Look for the missing adapter binding.</span></span> <span data-ttu-id="ae10d-506">次のセクションを追加、`bindingExtensions`バインドに応じて、不足しているアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-506">Add the following sections under the `bindingExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="ae10d-507">セットアップ ウィザードに任意登録に失敗した場合、すべてのバインドを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-507">You must register all the bindings if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="ae10d-508">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-508">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-509">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-509">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-510">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-510">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-511">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-511">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-512">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-512">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-513">公開キーを確認する方法については、次を参照してください。[公開キーとバージョン特定](#BKMK_PubKey)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-513">For information about how to determine the public key, see [Determine the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="ae10d-514">.NET Framework データ プロバイダーを登録します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-514">Register the .NET Framework data providers:</span></span>  
  
    1.  <span data-ttu-id="ae10d-515">検索、 `DbProviderFactories` system.data ノードの下の要素。</span><span class="sxs-lookup"><span data-stu-id="ae10d-515">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    2.  <span data-ttu-id="ae10d-516">不足している .NET Framework データ プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-516">Look for the missing .NET Framework Data Providers.</span></span> <span data-ttu-id="ae10d-517">下にある次のセクションを追加、`DbProviderFactories`ノード、不足しているプロバイダーによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-517">Add the following sections under the `DbProviderFactories` node, depending on the missing provider.</span></span> <span data-ttu-id="ae10d-518">セットアップ ウィザードに任意登録に失敗した場合は、すべてのプロバイダーを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-518">You must register all the providers if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="ae10d-519">[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-519">For the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-520">[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-520">For the [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="ae10d-521">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-521">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determine-the-public-key-and-version"></a><span data-ttu-id="ae10d-522">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-522">Determine the Public Key and Version</span></span>  
 <span data-ttu-id="ae10d-523">公開キーと、アダプターまたは .NET Framework Data Provider のバージョンを確認するのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-523">Complete the following steps to determine the public key and version for an adapter or the .NET Framework Data Provider.</span></span>  
  
###### <a name="determine-the-public-key"></a><span data-ttu-id="ae10d-524">公開キーを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-524">Determine the public key</span></span>  
  
1.  <span data-ttu-id="ae10d-525">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-525">Go to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="ae10d-526">対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-526">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="ae10d-527">次の表は、各アダプターおよびプロバイダーの Dll の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-527">The following table lists the name of the DLLs for each adapter and provider:</span></span>  
  
    |<span data-ttu-id="ae10d-528">アダプターと .NET Framework データ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="ae10d-528">Adapter/.NET Framework Data Provider</span></span>|<span data-ttu-id="ae10d-529">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="ae10d-529">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="ae10d-530">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="ae10d-530">Microsoft.Adapters.SAP</span></span>|  
    |[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="ae10d-531">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="ae10d-531">Microsoft.Adapters.Siebel</span></span>|  
    |[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="ae10d-532">Microsoft.Adapters.OracleDB</span><span class="sxs-lookup"><span data-stu-id="ae10d-532">Microsoft.Adapters.OracleDB</span></span>|  
    |[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="ae10d-533">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="ae10d-533">Microsoft.Adapters.OracleEBS</span></span>|  
    |[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="ae10d-534">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="ae10d-534">Microsoft.Adapters.Sql.dll</span></span>|  
    |[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="ae10d-535">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="ae10d-535">Microsoft.Data.SAPClient</span></span>|  
    |[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="ae10d-536">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="ae10d-536">Microsoft.Data.SiebelClient</span></span>|  
  
3.  <span data-ttu-id="ae10d-537">**全般** タブで、**公開キー トークンの**値は、DLL の公開キー。</span><span class="sxs-lookup"><span data-stu-id="ae10d-537">On the **General** tab, the **Public Key Token** values is the public key for the DLL.</span></span> <span data-ttu-id="ae10d-538">**バージョン**値は、DLL のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="ae10d-538">The **Version** value is the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="ae10d-539">公開キーをコピーし、**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-539">Copy the public key, and then select **Cancel**.</span></span>  
  
<a name="BKMK_InstallCustomRFC"></a>   
#### <a name="install-the-custom-rfcs"></a><span data-ttu-id="ae10d-540">カスタム Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-540">Install the custom RFCs</span></span>  
 <span data-ttu-id="ae10d-541">のみを使用する場合は、このタスクを実行する必要があります、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-541">You only need to do this task if you want to use the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="ae10d-542">カスタムの Rfc をインストールする方法の詳細については、次を参照してください。[カスタム Rfc のインストール](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)で、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="ae10d-542">For instructions on installing custom RFCs, see [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) in the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentation.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="ae10d-543">提供されるカスタム Rfc の以前のバージョンを使用しているかどうか、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、このリリースで提供、Rfc にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-543">If you are using an earlier version of the custom RFCs provided with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], then you must upgrade them to the RFCs provided with this release.</span></span> <span data-ttu-id="ae10d-544">以前の Rfc を削除することで、このリリースに付属し、Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-544">Do this by removing the earlier RFCs, and then installing the RFCs shipped with this release.</span></span>  

## <a name="installing-the-enterprise-applications"></a><span data-ttu-id="ae10d-545">エンタープライズ アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-545">Installing the Enterprise Applications</span></span>  
<span data-ttu-id="ae10d-546">手順と、別のエンタープライズの LOB システムをインストールするガイダンスお recommendnd、特定のインストールを使用する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-546">For the steps and guidance to install the different enterprise LOB systems, we recommendnd you use their specific installation guides.</span></span> <span data-ttu-id="ae10d-547">存在する場合は、特定の構成の変更は、アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae10d-547">Also refer to its adapter documentation for specific configuration changes, if any.</span></span>   

## <a name="installation-and-post-installation-checklist"></a><span data-ttu-id="ae10d-548">インストールおよびインストール後のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="ae10d-548">Installation and post-installation checklist</span></span>  
  
-   <span data-ttu-id="ae10d-549">すべてをインストールするかどうかを確認、[ソフトウェアの前提条件](#BKMK_Prereqs)正しいインストール オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-549">Make sure you installed all the [software prerequisites](#BKMK_Prereqs) with the correct installation option.</span></span>
  
-   <span data-ttu-id="ae10d-550">サポートされている、企業の LOB アプリケーションをインストールしたコンピューターにインストールされているバージョンであることを確認してください、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-550">Make sure you have the supported version of the enterprise LOB applications installed on your computer where you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ae10d-551">参照してください[エンタープライズ アプリケーションのバージョンがサポートされている](#BKMK_SuppLOB)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-551">See [Supported Enterprise Application Versions](#BKMK_SuppLOB).</span></span>  
  
-   <span data-ttu-id="ae10d-552">LOB システム接続するエンタープライズ用のアダプターのみをインストールするには、インストールしたを確認してください、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**カスタム**インストール オプションです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-552">To install only the adapter for the enterprise LOB system you want to connect, make sure you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Custom** installation option.</span></span> <span data-ttu-id="ae10d-553">インストールしていないことを確認、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**完了**インストール オプションです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-553">Make sure you have not installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Complete** installation option.</span></span> <span data-ttu-id="ae10d-554">参照してください[BizTalk Adapter Pack をインストールする](#BKMK_Install_Adap)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-554">See [Installing the BizTalk Adapter Pack](#BKMK_Install_Adap).</span></span>  
  
-   <span data-ttu-id="ae10d-555">SAP システムを使用して、tRFC の呼び出しを作成するかどうか、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、SQL Server データベースで、必要なテーブルを作成するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-555">If you want to make tRFC calls to the SAP system using the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], make sure you create the required tables in a SQL Server database.</span></span> <span data-ttu-id="ae10d-556">参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-556">See [After Installing the BizTalk Adapter Pack](#BKMK_PostInst).</span></span>
  
-   <span data-ttu-id="ae10d-557">実行中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードで、バインドを登録できませんでしたを示すエラー メッセージを取得可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-557">While running the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup wizard, you may get an error message that states the setup failed to register the bindings.</span></span> <span data-ttu-id="ae10d-558">場合は、手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-558">If so, register them manually.</span></span> <span data-ttu-id="ae10d-559">参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-559">See [After Installing the BizTalk Adapter Pack](#BKMK_PostInst).</span></span>  
  
-   <span data-ttu-id="ae10d-560">インストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、SAP システムにカスタムの Rfc をインストールするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-560">If you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure you install the custom RFCs on the SAP system.</span></span> <span data-ttu-id="ae10d-561">参照してください[BizTalk Adapter Pack をインストールした後](#BKMK_PostInst)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-561">See [After Installing the BizTalk Adapter Pack](#BKMK_PostInst).</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="change-the-biztalk-adapter-pack-installation"></a><span data-ttu-id="ae10d-562">BizTalk Adapter Pack のインストールを変更します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-562">Change the BizTalk Adapter Pack installation</span></span>  
 <span data-ttu-id="ae10d-563">変更するのには、次の手順を完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-563">Complete the following steps to change the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="ae10d-564">あるかどうかを確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]を変更するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-564">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="ae10d-565">変更することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード) で、またはサイレント モード (コマンド ライン) でインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-565">You can modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in interactive mode (the setup wizard), or in silent mode (the command line).</span></span>
  
#### <a name="change-the-bap-installation-in-interactive-mode"></a><span data-ttu-id="ae10d-566">対話モードで BAP インストールを変更します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-566">Change the BAP installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="ae10d-567">BizTalk Server 管理者グループのメンバーであるアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-567">Sign in using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="ae10d-568">**プログラムと機能****プログラムのアンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-568">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
3.  <span data-ttu-id="ae10d-569">右クリック**Microsoft BizTalk Adapter Pack**、し、**変更**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-569">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Change**.</span></span>  
  
4.  <span data-ttu-id="ae10d-570">[ようこそ] 画面で、次のように選択します。**次**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-570">On the Welcome screen, select **Next**.</span></span>  
  
5.  <span data-ttu-id="ae10d-571">**変更、修復、または削除インストール**:</span><span class="sxs-lookup"><span data-stu-id="ae10d-571">In **Change, repair, or remove installation**:</span></span>  
  
    -   <span data-ttu-id="ae10d-572">インストールするコンポーネントを選択する**変更**し、手順 6. に進みます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-572">To select the components you want to install, select **Change** and go to Step 6.</span></span>  
  
    -   <span data-ttu-id="ae10d-573">最新のインストールのエラーを修復するには、次のように選択します。**修復**手順 7. に進みます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-573">To repair errors in the most recent installation, select **Repair** and go to Step 7.</span></span>  
  
    -   <span data-ttu-id="ae10d-574">Microsoft を削除する[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、コンピューターから選択**削除**し、手順 10 に進みます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-574">To remove Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from the computer, select **Remove** and then go to Step 10.</span></span>  
  
6.  <span data-ttu-id="ae10d-575">場合は、インストールを変更することを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-575">If you chose to modify the installation:</span></span>  
  
    -   <span data-ttu-id="ae10d-576">展開して、 **Microsoft BizTalk Adapter Pack**ノード ベース アダプター、.NET Framework データ プロバイダー、またはその両方をインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-576">Expand the **Microsoft BizTalk Adapter Pack** node to choose to install the base adapters, the .NET Framework Data Providers, or both.</span></span>  
  
    -   <span data-ttu-id="ae10d-577">展開して、**ベース アダプター**ノードすべてのアダプターまたは特定のアダプターをインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-577">Expand the **Base Adapters** node to choose to install all the adapters or specific adapters.</span></span>  
  
    -   <span data-ttu-id="ae10d-578">展開して、 **ADO プロバイダー**ノードすべてのプロバイダーまたは特定のプロバイダーをインストールするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-578">Expand the **ADO Providers** node to choose to install all the providers or specific providers.</span></span>  
  
    -   <span data-ttu-id="ae10d-579">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-579">Select **Next**.</span></span>  
  
    -   <span data-ttu-id="ae10d-580">選択**変更**、し、**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-580">Select **Change**, and then select **Finish**.</span></span>  
  
7.  <span data-ttu-id="ae10d-581">インストールを修復して、選択した場合、 **Microsoft BizTalk Adapter Pack の修復の準備完了**ダイアログ ボックスで、**修復**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-581">If you chose to repair the installation, in the **Ready to repair Microsoft BizTalk Adapter Pack** dialog box, select **Repair**.</span></span> <span data-ttu-id="ae10d-582">ウィザードでは、インストールの修復を開始します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-582">The wizard starts repairing the installation.</span></span>  
  
8.  <span data-ttu-id="ae10d-583">必要に応じて、ユーザーの設定を変更、CEIP のオプトインに関連し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-583">If required, change your preferences regarding opting for CEIP, and then select **OK**.</span></span> 
  
9. <span data-ttu-id="ae10d-584">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-584">Select **Finish**.</span></span>  
  
10. <span data-ttu-id="ae10d-585">アダプターを削除した場合、 **Microsoft BizTalk Adapter Pack を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-585">If you chose to remove the adapters, in the **Ready to remove Microsoft BizTalk Adapter Pack** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
#### <a name="change-the-bap-installation-in-silent-mode"></a><span data-ttu-id="ae10d-586">サイレント モードで BAP インストールを変更します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-586">Change the BAP installation in silent mode</span></span>  
  
1.  <span data-ttu-id="ae10d-587">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-587">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="ae10d-588">次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-588">Run a command similar to the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-589">変更する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次のコマンドでの x64 ベースのプラットフォームにサイレント モードでインストールを交換して`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-589">To modify the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in a silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     <span data-ttu-id="ae10d-590">このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]をインストールし、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-590">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], and installs the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)].</span></span>  
  
     <span data-ttu-id="ae10d-591">別の値を使用して、`REMOVE`と`ADDLOCAL`プロパティを追加または特定のコンポーネントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-591">By using different values for the `REMOVE` and `ADDLOCAL` properties, you can add or remove specific components.</span></span> <span data-ttu-id="ae10d-592">内のテーブルを参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(このトピック) でこれらのプロパティを使用できる値についてはします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-592">Refer to the table in [Installing the BizTalk Adapter Pack in Silent Mode](#BKMK_SilentInst) (in this topic) for information about the values that you can use for these properties.</span></span>  
  
     <span data-ttu-id="ae10d-593">Msiexec コマンドの一部として、/f オプションを使用して、サイレントの修復を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-593">You can also do a silent repair by using the /f option as part of the msiexec command.</span></span> <span data-ttu-id="ae10d-594">例:</span><span class="sxs-lookup"><span data-stu-id="ae10d-594">For example:</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     <span data-ttu-id="ae10d-595">さまざまなさまざまな組み合わせを使用するには、/f オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-595">You can use various different combinations with the /f option.</span></span> <span data-ttu-id="ae10d-596">Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-596">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="ae10d-597">移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-597">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ae10d-598">変更中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでインストールで CEIP を有効または無効にするための設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae10d-598">While modifying the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="ae10d-599">True または false に、CEIP_OPTIN を明示的に設定した場合でも、インストールは残りの中に選択した環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-599">The preferences you chose during the installation remains, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="removing-the-biztalk-adapter-pack"></a><span data-ttu-id="ae10d-600">BizTalk アダプター パックを削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-600">Removing the BizTalk Adapter Pack</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae10d-601">TRFC 機能を使用する SQL Server データベースでテーブルを作成した場合、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除する前に手動で削除する必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-601">If you created tables in the SQL Server database to work with the tRFC feature of the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], you must manually remove them before removing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ae10d-602">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールは、通常は SapAdapter DbScript-Uninstall.sql ファイルをコピー\<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-602">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation copies a SapAdapter-DbScript-Uninstall.sql file typically at \<installation drive>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ae10d-603">作成したテーブルを削除するには、このファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-603">Run this file to remove the tables you created.</span></span>  
  
<span data-ttu-id="ae10d-604">次の手順を削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]コンピューターからです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-604">Complete the following steps to remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] from your computer.</span></span> <span data-ttu-id="ae10d-605">あるかどうかを確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]アダプターを削除するセットアップ ウィザードを実行する前にインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-605">Make sure you have the [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the adapters.</span></span>  
  
 <span data-ttu-id="ae10d-606">削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード) またはサイレント モード (コマンド ライン)。</span><span class="sxs-lookup"><span data-stu-id="ae10d-606">You can remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in interactive mode (setup wizard), or in silent mode (command line).</span></span>
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-interactive-mode"></a><span data-ttu-id="ae10d-607">対話モードで BizTalk Adapter Pack をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-607">Uninstall the BizTalk Adapter Pack in interactive mode</span></span>  
  
1.  <span data-ttu-id="ae10d-608">**プログラムと機能****プログラムのアンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-608">In **Programs and features**, select **Uninstall a program**.</span></span>  
  
2.  <span data-ttu-id="ae10d-609">右クリック**Microsoft BizTalk Adapter Pack**、し、**アンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-609">Right-click **Microsoft BizTalk Adapter Pack**, and then select **Uninstall**.</span></span>  
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-silent-mode"></a><span data-ttu-id="ae10d-610">サイレント モードで BizTalk Adapter Pack をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-610">Uninstall the BizTalk Adapter Pack in silent mode</span></span>  
  
1.  <span data-ttu-id="ae10d-611">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-611">Open a command prompt, and go to the root directory of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="ae10d-612">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-612">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae10d-613">削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードで、次のコマンドの x64 ベースのプラットフォーム上で置き換える`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-613">To remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] in silent mode on an x64-based platform, in the following commands, replace `AdaptersSetup.msi` with `AdaptersSetup64.msi`.</span></span>  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     <span data-ttu-id="ae10d-614">このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]から、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-614">This command removes the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)] from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
     <span data-ttu-id="ae10d-615">異なる値を提供することによって、`REMOVE`プロパティから特定のコンポーネントを削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-615">By providing different values for the `REMOVE` property, you can remove specific components from the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="ae10d-616">内のテーブルを参照してください[サイレント モードで BizTalk Adapter Pack をインストールする](#BKMK_SilentInst)(このトピック) でこのプロパティの使用できる値についてはします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-616">Refer to the table in [Installing the BizTalk Adapter Pack in Silent Mode](#BKMK_SilentInst) (in this topic) for information about the values that you can use for this property.</span></span>  
  
     <span data-ttu-id="ae10d-617">完全に削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-617">To completely remove the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], execute the following command:</span></span>  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     <span data-ttu-id="ae10d-618">Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-618">For more information about the msiexec command type `msiexec` on the command line, and press `ENTER`.</span></span> <span data-ttu-id="ae10d-619">移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-619">Or go to [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).</span></span>
  
<a name="BKMK_PostRemove"></a>   
### <a name="after-removing-the-biztalk-adapter-pack"></a><span data-ttu-id="ae10d-620">BizTalk Adapter Pack を削除した後</span><span class="sxs-lookup"><span data-stu-id="ae10d-620">After removing the BizTalk Adapter Pack</span></span>  
 <span data-ttu-id="ae10d-621">削除した後、次の手順を実行する必要があります、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ae10d-621">You may need to perform the following steps after removing the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="ae10d-622">そのためには、セットアップ ウィザードが失敗した場合、アダプターのバインドまたは .NET Framework Data Provider の登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-622">Remove the adapter bindings or the .NET Framework Data Provider registration, if the setup wizard failed to do so</span></span>
  
-   <span data-ttu-id="ae10d-623">インストールする場合は、カスタムの Rfc を削除します[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae10d-623">Remove the custom RFCs, if you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]</span></span>
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="remove-the-bindings-or-the-net-framework-data-provider-registration"></a><span data-ttu-id="ae10d-624">バインドまたは .NET Framework データ プロバイダーの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-624">Remove the bindings or the .NET Framework Data Provider registration</span></span>  
 <span data-ttu-id="ae10d-625">次の手順を完了*のみ*machine.config ファイルから、アダプターのバインドまたは .NET Framework Data Provider の登録を削除するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="ae10d-625">Complete these steps *only* if the setup wizard fails to remove the adapter bindings or .NET Framework Data Provider registration from the machine.config file.</span></span>  
  
###### <a name="remove-the-adapter-bindings-or-net-framework-data-provider-registration"></a><span data-ttu-id="ae10d-626">アダプターのバインドまたは .NET Framework Data Provider の登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-626">Remove the adapter bindings or .NET Framework Data Provider registration</span></span>  
  
1.  <span data-ttu-id="ae10d-627">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-627">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="ae10d-628">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-628">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
2.  <span data-ttu-id="ae10d-629">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-629">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="ae10d-630">アダプターのバインドの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-630">Remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="ae10d-631">検索、`system.serviceModel`要素、および要素の下には、次の削除。</span><span class="sxs-lookup"><span data-stu-id="ae10d-631">Search for the `system.serviceModel` element, and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="ae10d-632">検索、 `bindingElementExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="ae10d-632">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="ae10d-633">次のセクションでは、削除、`bindingElementExtensions`バインドに応じて、使用可能なアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-633">Remove the following sections under the `bindingElementExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="ae10d-634">セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-634">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="ae10d-635">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-635">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-636">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-636">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-637">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-637">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-638">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-638">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-639">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-639">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="ae10d-640">検索、 `bindingExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="ae10d-640">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="ae10d-641">次のセクションでは、削除、`bindingExtensions`バインドに応じて、使用可能なアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-641">Remove the following sections under the `bindingExtensions` node, depending on the available adapter binding.</span></span> <span data-ttu-id="ae10d-642">セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-642">You must remove all the bindings if the setup wizard fails to remove any.</span></span>  
  
         <span data-ttu-id="ae10d-643">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-643">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-644">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-644">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-645">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-645">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], remove:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-646">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-646">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-647">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-647">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="ae10d-648">.NET Framework データ プロバイダーの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-648">Remove the .NET Framework Data Provider registration:</span></span>  
  
    -   <span data-ttu-id="ae10d-649">検索、 `DbProviderFactories` system.data ノードの下の要素。</span><span class="sxs-lookup"><span data-stu-id="ae10d-649">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    -   <span data-ttu-id="ae10d-650">まだ登録されている .NET Framework データ プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-650">Look for the .NET Framework Data Providers that are still registered.</span></span> <span data-ttu-id="ae10d-651">次のセクションでは、削除、`DbProviderFactories`によっては、既存の .NET Framework データ プロバイダーのノード。</span><span class="sxs-lookup"><span data-stu-id="ae10d-651">Remove the following sections under the `DbProviderFactories` node, depending on the existing .NET Framework Data Providers.</span></span> <span data-ttu-id="ae10d-652">存在する場合は、すべてのプロバイダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-652">You must remove all the providers if they exist.</span></span>  
  
         <span data-ttu-id="ae10d-653">[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-653">For [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="ae10d-654">[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-654">For [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="ae10d-655">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="ae10d-655">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_Remove_SAP_Pro"></a>   
#### <a name="remove-the-custom-rfcs"></a><span data-ttu-id="ae10d-656">カスタム Rfc を削除します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-656">Remove the custom RFCs</span></span>  
<span data-ttu-id="ae10d-657">SAP システムにインストールされているカスタム Rfc を削除するには、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-657">Complete this step to remove the custom RFCs that you installed in the SAP system.</span></span> <span data-ttu-id="ae10d-658">参照してください[インストールまたは削除するカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-658">See [Install or remove custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
## <a name="troubleshoot-biztalk-adapter-pack-installation"></a><span data-ttu-id="ae10d-659">BizTalk Adapter Pack のインストールをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="ae10d-659">Troubleshoot BizTalk Adapter Pack installation</span></span>  
 <span data-ttu-id="ae10d-660">インストールするときに直面する問題のいくつかは次のとおり[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-660">Following are some issues that you might face when installing [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ae10d-661">包括のインストールに関連する問題の一覧を表示するを参照してください**トラブルシューティング**アダプターごとにトピックです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-661">For a comprehensive list of installation-related issues, refer to **Troublehsooting** topics for each adapter.</span></span>  
  
-   <span data-ttu-id="ae10d-662">**64 ビット コンピューターでセットアップを実行してエラーが発生するスキーマ ファイルへのアクセス中には**</span><span class="sxs-lookup"><span data-stu-id="ae10d-662">**Running setup on a 64-bit computer might throw an error while accessing schema file**</span></span>  
  
     <span data-ttu-id="ae10d-663">[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップへのアクセス中にエラーをスローする、  **Microsoft.Adapters* 。\<AdapterName >*_schema.xml** ファイルが、アダプターのインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="ae10d-663">The [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup throws an error while accessing the **Microsoft.Adapters.*\<AdapterName>*_schema.xml** file, but proceeds with the adapter installation.</span></span>  
  
     <span data-ttu-id="ae10d-664">**原因**</span><span class="sxs-lookup"><span data-stu-id="ae10d-664">**Cause**</span></span>  
  
     <span data-ttu-id="ae10d-665">場合は 32 ビットと 64 ビットの両方のバージョン、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]がインストールされている同じコンピューター両方で使用されるターゲットのスキーマ ファイルは同じです。</span><span class="sxs-lookup"><span data-stu-id="ae10d-665">If both 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] are installed on the same computer, the target schema file used by both is the same.</span></span> <span data-ttu-id="ae10d-666">その結果、ファイルは、32 ビットでインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]64 ビットのインストーラーが、アクセスしようとするときに、IIS によって使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae10d-666">As a result, the file installed by the 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] might be in use by IIS when the 64-bit installer tries to access it.</span></span>  
  
     <span data-ttu-id="ae10d-667">**解決策**</span><span class="sxs-lookup"><span data-stu-id="ae10d-667">**Resolution**</span></span>  
  
     <span data-ttu-id="ae10d-668">手動でコピー、  **Microsoft.Adapters* 。\<AdapterName >*_schema.xml** ファイルから`C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`"に`C:\Windows\System32\inetsrv\config\schema`です。</span><span class="sxs-lookup"><span data-stu-id="ae10d-668">Manually copy the **Microsoft.Adapters.*\<AdapterName>*_schema.xml** file from `C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`" to `C:\Windows\System32\inetsrv\config\schema`.</span></span>  