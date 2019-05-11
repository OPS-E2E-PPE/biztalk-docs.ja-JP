---
title: サービス アダプターを Windows SharePoint の問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c29569-3814-43a7-93f8-a39c3464a831
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5451a4fffd4c75b52f46741b1e7228dacf9f6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385211"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="5d2c2-102">Windows SharePoint Services アダプターに関する問題を診断する方法</span><span class="sxs-lookup"><span data-stu-id="5d2c2-102">How to Diagnose Problems with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="5d2c2-103">このセクションには、Windows Sharepoint Services アダプターに関する問題の診断に役立つことができますの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d2c2-103">This section contains steps that can be followed to help diagnose problems with the Windows Sharepoint Services adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="5d2c2-104">IIS および HTTPERR ログ ファイルの IIS サーバーのエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5d2c2-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="5d2c2-105">ソースまたはターゲット IIS サーバーのログ ファイルは、Windows Sharepoint Services アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5d2c2-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the Windows Sharepoint Services adapter.</span></span> <span data-ttu-id="5d2c2-106">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="5d2c2-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="5d2c2-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="5d2c2-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5d2c2-108">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="5d2c2-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
- <span data-ttu-id="5d2c2-109">既定では、HTTPERR ログ ファイル、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]ベースのコンピューターは、次のディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5d2c2-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="5d2c2-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="5d2c2-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5d2c2-111">HTTPERR ログ ファイルが収録のみ[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="5d2c2-111">The HTTPERR log file is only available on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2c2-112">参照</span><span class="sxs-lookup"><span data-stu-id="5d2c2-112">See Also</span></span>  
 <span data-ttu-id="5d2c2-113">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="5d2c2-113">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="5d2c2-114">Windows SharePoint Services アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5d2c2-114">Troubleshooting the Windows SharePoint Services Adapter</span></span>](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)