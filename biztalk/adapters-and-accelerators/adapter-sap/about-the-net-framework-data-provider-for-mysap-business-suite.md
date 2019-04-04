---
title: .NET Framework Data Provider for mySAP Business Suite について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ee712f6b818b94ca731d94165cd345a3249a61d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978915"
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="3eb92-102">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="3eb92-102">About the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="3eb92-103">このセクションでは、に関する情報を提供、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) とその機能。</span><span class="sxs-lookup"><span data-stu-id="3eb92-103">This section provides information about the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) and its features.</span></span> <span data-ttu-id="3eb92-104">使用する方法については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[、.NET Framework Data Provider for mySAP Business Suite を使用して、](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="3eb92-104">For instructions about how to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3eb92-105">インストールする場合でも、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]の一部として、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 、インストール、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムでカスタム RFC をインストールするまではまだ完了しません。</span><span class="sxs-lookup"><span data-stu-id="3eb92-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, your [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] is still incomplete until you install a custom RFC in the SAP system.</span></span> <span data-ttu-id="3eb92-106">カスタム RFC をインストールする方法の手順については、[Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eb92-106">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="3eb92-107">使用することができます、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3eb92-107">You can use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] in the following ways:</span></span>  
  
- <span data-ttu-id="3eb92-108">SAP システムへの接続に、ADO.NET クライアントの作成</span><span class="sxs-lookup"><span data-stu-id="3eb92-108">To write an ADO.NET client to connect to the SAP system.</span></span> <span data-ttu-id="3eb92-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]プロバイダーとやり取りするための特定のクラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="3eb92-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
- <span data-ttu-id="3eb92-110">SAP システムで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3eb92-110">To execute a SELECT query on the SAP system.</span></span> <span data-ttu-id="3eb92-111">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこの機能をカスタム RFC を使用します。</span><span class="sxs-lookup"><span data-stu-id="3eb92-111">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the custom RFC for this feature.</span></span>  
  
- <span data-ttu-id="3eb92-112">SAP システムで EXEC 処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="3eb92-112">To execute an EXEC operation on the SAP system.</span></span> <span data-ttu-id="3eb92-113">この操作を使用すると、SAP システムに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3eb92-113">You can use this operation to perform queries on the SAP system.</span></span>  
  
- <span data-ttu-id="3eb92-114">SAP システムでの EXECQUERY 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3eb92-114">To execute an EXECQUERY operation on the SAP system.</span></span> <span data-ttu-id="3eb92-115">この操作を使用して、SAP システムで既に定義されているクエリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3eb92-115">You can use this operation to execute queries that are already defined in the SAP system.</span></span>  
  
- <span data-ttu-id="3eb92-116">さらを使用する、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX SAP システムから画面のテーブルと関数モジュールをプラグインします。</span><span class="sxs-lookup"><span data-stu-id="3eb92-116">To, in turn, use the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in to surface tables and function modules from the SAP system.</span></span> <span data-ttu-id="3eb92-117">SAP システムから検出されるオブジェクトの名前は、構成ファイル、SAPDiscoveredObjects.xml に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3eb92-117">The names of the objects discovered from the SAP system are written to a configuration file, SAPDiscoveredObjects.xml.</span></span>  
  
- <span data-ttu-id="3eb92-118">使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Integration Services (SSIS) とします。</span><span class="sxs-lookup"><span data-stu-id="3eb92-118">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Integration Services (SSIS).</span></span>  
  
- <span data-ttu-id="3eb92-119">使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Reporting Services (SSRS) とします。</span><span class="sxs-lookup"><span data-stu-id="3eb92-119">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Reporting Services (SSRS).</span></span>  
  
  <span data-ttu-id="3eb92-120">これらのタスクの実行の詳細については、[、.NET Framework Data Provider for mySAP Business Suite を使用して、](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eb92-120">For more information about performing these tasks, see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span> <span data-ttu-id="3eb92-121">カスタム RFC、SAPDiscoveredObjects.xml 構成ファイルに関連付けられている制限事項の詳細については、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eb92-121">For more information about the custom RFC, the SAPDiscoveredObjects.xml configuration file, and the limitations associated with the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see the following links.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3eb92-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3eb92-122">In This Section</span></span>  
  
-   [<span data-ttu-id="3eb92-123">SAP でプロバイダーによって使用されるカスタム Rfc</span><span class="sxs-lookup"><span data-stu-id="3eb92-123">Custom RFCs Used by the Provider in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [<span data-ttu-id="3eb92-124">SAP で SAPDiscoveredObjects.xml ファイルについて</span><span class="sxs-lookup"><span data-stu-id="3eb92-124">About the SAPDiscoveredObjects.xml File in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [<span data-ttu-id="3eb92-125">.NET Framework Data Provider for mySAP Business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="3eb92-125">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)