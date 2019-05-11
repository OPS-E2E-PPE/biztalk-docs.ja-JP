---
title: SOAP アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c93333-cb32-49bc-a1c4-9d726ab41850
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b0339f44827dd716afc517ed3aeb8aca9c25e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385241"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a><span data-ttu-id="6db07-102">SOAP アダプターに関する問題を診断する方法</span><span class="sxs-lookup"><span data-stu-id="6db07-102">How to Diagnose Problems with the SOAP Adapter</span></span>
<span data-ttu-id="6db07-103">このセクションには、SOAP アダプターに関する問題の診断に役立つことができますの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6db07-103">This section contains steps that can be followed to help diagnose problems with the SOAP adapter.</span></span>  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a><span data-ttu-id="6db07-104">IIS ログと IIS サーバーのエラーの HTTPERR ログを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6db07-104">Check the IIS log and HTTPERR log of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="6db07-105">ソースまたはターゲット IIS サーバーのログ ファイルは、SOAP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6db07-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the SOAP adapter.</span></span> <span data-ttu-id="6db07-106">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="6db07-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="6db07-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="6db07-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6db07-108">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="6db07-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="6db07-109">既定では、HTTPERR ログ ファイル、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]ベースのコンピューターは、次のディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6db07-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="6db07-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="6db07-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6db07-111">HTTPERR ログ ファイルは上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="6db07-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db07-112">参照</span><span class="sxs-lookup"><span data-stu-id="6db07-112">See Also</span></span>  
 <span data-ttu-id="6db07-113">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="6db07-113">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="6db07-114">SOAP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6db07-114">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)