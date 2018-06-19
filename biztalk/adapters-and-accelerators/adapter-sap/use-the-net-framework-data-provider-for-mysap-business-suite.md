---
title: .NET Framework データ プロバイダーを使用して、mySAP Business Suite の |Microsoft ドキュメント
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
ms.openlocfilehash: faa813fa6218d5afcb470406097d745ddf93522b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217194"
---
# <a name="use-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="9329b-102">使用して、.NET Framework Data Provider 用 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="9329b-102">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="9329b-103">このセクションの内容については、手順を使用して、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9329b-103">This section provides instructions on using the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="9329b-104">によって使用されるカスタム RFC について[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]プロバイダーの制限事項を参照してください、[について、.NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="9329b-104">For information about the custom RFC used by [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] and the limitations of the provider see [About the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9329b-105">インストールする選択した場合でも、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール、使用する SAP システムで一部のカスタム Rfc をインストールする必要があります、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9329b-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, you must install some custom RFCs at the SAP system to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="9329b-106">カスタムの Rfc をインストールする方法の手順については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="9329b-106">For instructions on how to install the custom RFCs, see [Installing Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9329b-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9329b-107">In This Section</span></span>  
  
-   [<span data-ttu-id="9329b-108">SAP アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="9329b-108">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="9329b-109">SAP 接続文字列のデータ プロバイダーの種類の説明を読む</span><span class="sxs-lookup"><span data-stu-id="9329b-109">Read about Data Provider types for the SAP Connection String</span></span>](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)  
  
-   [<span data-ttu-id="9329b-110">SAP の SELECT ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="9329b-110">Syntax for a SELECT Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)  
  
-   [<span data-ttu-id="9329b-111">SAP の EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="9329b-111">Syntax for an EXEC Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)  
  
-   [<span data-ttu-id="9329b-112">SAP クエリの実行のサポート</span><span class="sxs-lookup"><span data-stu-id="9329b-112">Support for Executing SAP Queries</span></span>](https://msdn.microsoft.com/library/dd788118.aspx)  
  
-   [<span data-ttu-id="9329b-113">呼び出し元の Rfc および Bapi の SAP の EXEC コマンドを使用して、</span><span class="sxs-lookup"><span data-stu-id="9329b-113">Invoking RFCs and BAPIs by using the EXEC Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)  
  
-   [<span data-ttu-id="9329b-114">SAP の SELECT コマンドを使用してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9329b-114">Performing a Query by using the SELECT Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/run-a-query-using-the-select-command-in-sap.md)  
  
-   [<span data-ttu-id="9329b-115">EXECQUERY コマンドを使用して SAP クエリの実行</span><span class="sxs-lookup"><span data-stu-id="9329b-115">Executing an SAP Query Using the EXECQUERY Command</span></span>](../../adapters-and-accelerators/adapter-sap/execute-an-sap-query-using-the-execquery-command.md)  
  
-   [<span data-ttu-id="9329b-116">DDEX プラグインと SAP 用データ プロバイダーを使用</span><span class="sxs-lookup"><span data-stu-id="9329b-116">Using the Data Provider for SAP with the DDEX Plug-in</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)  
  
-   [<span data-ttu-id="9329b-117">SAP と SSIS のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9329b-117">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)  
  
-   [<span data-ttu-id="9329b-118">SSRS と SAP 用データ プロバイダーを使用</span><span class="sxs-lookup"><span data-stu-id="9329b-118">Using the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)