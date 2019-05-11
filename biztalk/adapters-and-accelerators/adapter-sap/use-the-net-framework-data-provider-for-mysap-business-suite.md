---
title: .NET Framework データ プロバイダーを使用して、mySAP Business Suite の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DDEX plug-in
- NET Framework Data Provider for mySAP Business Suite
- function module
- SSIS
- installation
- EXEC query
- SELECT query
- SAPDiscoveredObjects.xml
- SQL Server Integration Services
- Data Provider for SAP
- custom RFC
- installing
- configuration file
ms.assetid: 3abe9c34-b81b-4c0a-9bfd-bf05f89f29b8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c743be7e38186c0435c91ba22fd61ad4353d1b84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372082"
---
# <a name="use-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="317dc-102">使用して、.NET Framework Data Provider for mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="317dc-102">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="317dc-103">このセクションで使用方法については、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="317dc-103">This section provides instructions on using the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="317dc-104">使用されるカスタム RFC について[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]プロバイダーの制限事項を参照してくださいと[について、.NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="317dc-104">For information about the custom RFC used by [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] and the limitations of the provider see [About the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="317dc-105">インストールする場合でも、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール、使用する SAP システムでいくつかのカスタム Rfc をインストールする必要があります、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="317dc-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, you must install some custom RFCs at the SAP system to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="317dc-106">カスタム Rfc をインストールする方法の手順については、次を参照してください。 [Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="317dc-106">For instructions on how to install the custom RFCs, see [Installing Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="317dc-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="317dc-107">In This Section</span></span>  
  
-   [<span data-ttu-id="317dc-108">SAP アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="317dc-108">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="317dc-109">SAP 接続文字列のデータ プロバイダーの種類をについてください。</span><span class="sxs-lookup"><span data-stu-id="317dc-109">Read about Data Provider types for the SAP Connection String</span></span>](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)  
  
-   [<span data-ttu-id="317dc-110">SAP の SELECT ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="317dc-110">Syntax for a SELECT Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)  
  
-   [<span data-ttu-id="317dc-111">SAP の EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="317dc-111">Syntax for an EXEC Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)  
  
-   [<span data-ttu-id="317dc-112">SAP クエリの実行のサポート</span><span class="sxs-lookup"><span data-stu-id="317dc-112">Support for Executing SAP Queries</span></span>](https://msdn.microsoft.com/library/dd788118.aspx)  
  
-   [<span data-ttu-id="317dc-113">SAP の EXEC コマンドを使用して Rfc と Bapi を呼び出す</span><span class="sxs-lookup"><span data-stu-id="317dc-113">Invoking RFCs and BAPIs by using the EXEC Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)  
  
-   [<span data-ttu-id="317dc-114">SAP で SELECT コマンドを使用してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="317dc-114">Performing a Query by using the SELECT Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/run-a-query-using-the-select-command-in-sap.md)  
  
-   [<span data-ttu-id="317dc-115">EXECQUERY コマンドを使用して SAP クエリの実行</span><span class="sxs-lookup"><span data-stu-id="317dc-115">Executing an SAP Query Using the EXECQUERY Command</span></span>](../../adapters-and-accelerators/adapter-sap/execute-an-sap-query-using-the-execquery-command.md)  
  
-   [<span data-ttu-id="317dc-116">DDEX プラグインで SAP 用データ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="317dc-116">Using the Data Provider for SAP with the DDEX Plug-in</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)  
  
-   [<span data-ttu-id="317dc-117">Data Provider for SAP を SSIS と一緒にの使用</span><span class="sxs-lookup"><span data-stu-id="317dc-117">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)  
  
-   [<span data-ttu-id="317dc-118">Data Provider for SAP を SSRS と一緒にの使用</span><span class="sxs-lookup"><span data-stu-id="317dc-118">Using the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)