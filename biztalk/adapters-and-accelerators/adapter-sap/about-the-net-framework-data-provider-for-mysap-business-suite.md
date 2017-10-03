---
title: ".NET Framework Data Provider for mySAP Business Suite |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSIS
- EXEC query
- SELECT query
- SAPDiscoveredObjects.xml
- SQL Server Integration Services
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- custom RFC
- Visual Studio DDEX plug-in
ms.assetid: 4832f789-c1d8-4c5d-a49d-b1da6b7d4bd4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf6b8a1657f0731fc09c4ebc1ef1fa99e0e6ae4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="55422-102">.NET Framework Data Provider for mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="55422-102">About the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="55422-103">このセクションの内容に関する情報を提供する、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) とその機能します。</span><span class="sxs-lookup"><span data-stu-id="55422-103">This section provides information about the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) and its features.</span></span> <span data-ttu-id="55422-104">使用する方法については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[mySAP Business Suite の .NET Framework データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="55422-104">For instructions about how to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55422-105">インストールする選択した場合でも、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]の一部として、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 、インストール、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]は、SAP システムでカスタム RFC をインストールするまで、まだ完了します。</span><span class="sxs-lookup"><span data-stu-id="55422-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, your [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] is still incomplete until you install a custom RFC in the SAP system.</span></span> <span data-ttu-id="55422-106">カスタムの RFC をインストールする方法の手順については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="55422-106">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="55422-107">使用することができます、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のようにします。</span><span class="sxs-lookup"><span data-stu-id="55422-107">You can use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="55422-108">書き込む場合、SAP システムへの接続に、ADO.NET クライアント。</span><span class="sxs-lookup"><span data-stu-id="55422-108">To write an ADO.NET client to connect to the SAP system.</span></span> <span data-ttu-id="55422-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]プロバイダーとのインターフェイスを有効にする特定のクラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="55422-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
-   <span data-ttu-id="55422-110">SAP システムで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="55422-110">To execute a SELECT query on the SAP system.</span></span> <span data-ttu-id="55422-111">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこの機能をカスタム RFC を使用します。</span><span class="sxs-lookup"><span data-stu-id="55422-111">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the custom RFC for this feature.</span></span>  
  
-   <span data-ttu-id="55422-112">SAP システムに対して EXEC 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55422-112">To execute an EXEC operation on the SAP system.</span></span> <span data-ttu-id="55422-113">この操作を使用すると、SAP システムに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="55422-113">You can use this operation to perform queries on the SAP system.</span></span>  
  
-   <span data-ttu-id="55422-114">SAP システムに対して EXECQUERY 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55422-114">To execute an EXECQUERY operation on the SAP system.</span></span> <span data-ttu-id="55422-115">この操作を使用して、SAP システムで既に定義されているクエリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="55422-115">You can use this operation to execute queries that are already defined in the SAP system.</span></span>  
  
-   <span data-ttu-id="55422-116">さらに、使用する、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX SAP システムから画面のテーブルと関数モジュールにプラグインします。</span><span class="sxs-lookup"><span data-stu-id="55422-116">To, in turn, use the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in to surface tables and function modules from the SAP system.</span></span> <span data-ttu-id="55422-117">SAP システムから検出されるオブジェクトの名前は、構成ファイル、SAPDiscoveredObjects.xml に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="55422-117">The names of the objects discovered from the SAP system are written to a configuration file, SAPDiscoveredObjects.xml.</span></span>  
  
-   <span data-ttu-id="55422-118">使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Integration Services (SSIS) にします。</span><span class="sxs-lookup"><span data-stu-id="55422-118">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Integration Services (SSIS).</span></span>  
  
-   <span data-ttu-id="55422-119">使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Reporting Services (SSRS) とします。</span><span class="sxs-lookup"><span data-stu-id="55422-119">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Reporting Services (SSRS).</span></span>  
  
 <span data-ttu-id="55422-120">これらのタスクを実行する方法の詳細については、次を参照してください。 [mySAP Business Suite の .NET Framework データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="55422-120">For more information about performing these tasks, see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span> <span data-ttu-id="55422-121">カスタム RFC、SAPDiscoveredObjects.xml 構成ファイルに関連付けられている制限事項の詳細については、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55422-121">For more information about the custom RFC, the SAPDiscoveredObjects.xml configuration file, and the limitations associated with the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see the following links.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55422-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="55422-122">In This Section</span></span>  
  
-   [<span data-ttu-id="55422-123">SAP のプロバイダーによって使用されるカスタム Rfc</span><span class="sxs-lookup"><span data-stu-id="55422-123">Custom RFCs Used by the Provider in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [<span data-ttu-id="55422-124">SAP の SAPDiscoveredObjects.xml ファイルについて</span><span class="sxs-lookup"><span data-stu-id="55422-124">About the SAPDiscoveredObjects.xml File in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [<span data-ttu-id="55422-125">.NET Framework Data Provider for mySAP Business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="55422-125">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)