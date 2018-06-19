---
title: Data Provider 用 Siebel に関する問題のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, troubleshooting
- troubleshooting, Data Provider for Siebel
ms.assetid: 2bfe69a2-d6de-466d-9f36-f11c386c771c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6e100635b1cb2db5c78ff713c8e6ad32d4e7d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222002"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a><span data-ttu-id="086e3-102">Data Provider 用 Siebel に関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="086e3-102">Troubleshoot Issues with the Data Provider for Siebel</span></span>
<span data-ttu-id="086e3-103">このセクションで説明を使用する場合に発生する可能性のあるエラーを解決するのには、トラブルシューティングの手法を使用して、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="086e3-103">This section discusses using troubleshooting techniques to resolve errors that you might encounter when using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="086e3-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="086e3-104">Known Issues</span></span>  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a><span data-ttu-id="086e3-105">Data Provider 用 Siebel は「コンポーネント 'DataReader ソース' (380)」エラーになります</span><span class="sxs-lookup"><span data-stu-id="086e3-105">Data Provider for Siebel may give "component 'DataReader Source' (380)" error</span></span>  
 <span data-ttu-id="086e3-106">**問題**</span><span class="sxs-lookup"><span data-stu-id="086e3-106">**Problem**</span></span>  
  
 <span data-ttu-id="086e3-107">Siebel ビジネス コンポーネントで SELECT クエリを実行中に、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 「コンポーネント 'DataReader ソース' (380)」エラーになります。</span><span class="sxs-lookup"><span data-stu-id="086e3-107">While performing a SELECT query on a Siebel business component, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] may give a "component 'DataReader Source' (380)" error.</span></span>  
  
 <span data-ttu-id="086e3-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="086e3-108">**Cause**</span></span>  
  
 <span data-ttu-id="086e3-109">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]パラメーターの Siebel システムから受信した値が、maxLength、パラメーターのプロパティを超えた場合、このエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="086e3-109">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] gives this error if the value received from the Siebel system for a parameter exceeds the maxLength property for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086e3-110">参照</span><span class="sxs-lookup"><span data-stu-id="086e3-110">See Also</span></span>  
[<span data-ttu-id="086e3-111">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="086e3-111">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)