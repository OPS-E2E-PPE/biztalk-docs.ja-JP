---
title: Data Provider for Siebel に関する問題のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: adeae6cc42aebb1ddae3c3c3e769fdb77984d878
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370442"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a><span data-ttu-id="d4a79-102">Data Provider for Siebel に関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d4a79-102">Troubleshoot Issues with the Data Provider for Siebel</span></span>
<span data-ttu-id="d4a79-103">このセクションを使用する場合に発生する可能性のあるエラーを解決するトラブルシューティングの手法を使用して説明します、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="d4a79-103">This section discusses using troubleshooting techniques to resolve errors that you might encounter when using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="d4a79-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d4a79-104">Known Issues</span></span>  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a><span data-ttu-id="d4a79-105">Data Provider for Siebel「コンポーネント 'DataReader ソース' (380)」エラーを与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4a79-105">Data Provider for Siebel may give "component 'DataReader Source' (380)" error</span></span>  
 <span data-ttu-id="d4a79-106">**問題**</span><span class="sxs-lookup"><span data-stu-id="d4a79-106">**Problem**</span></span>  
  
 <span data-ttu-id="d4a79-107">Siebel ビジネス コンポーネントで SELECT クエリを実行中に、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 「コンポーネント 'DataReader ソース' (380)」エラーを与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4a79-107">While performing a SELECT query on a Siebel business component, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] may give a "component 'DataReader Source' (380)" error.</span></span>  
  
 <span data-ttu-id="d4a79-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4a79-108">**Cause**</span></span>  
  
 <span data-ttu-id="d4a79-109">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]パラメーターの Siebel システムから受信した値は、パラメーターの maxLength プロパティを超えています。 このエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="d4a79-109">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] gives this error if the value received from the Siebel system for a parameter exceeds the maxLength property for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a79-110">参照</span><span class="sxs-lookup"><span data-stu-id="d4a79-110">See Also</span></span>  
[<span data-ttu-id="d4a79-111">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d4a79-111">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)