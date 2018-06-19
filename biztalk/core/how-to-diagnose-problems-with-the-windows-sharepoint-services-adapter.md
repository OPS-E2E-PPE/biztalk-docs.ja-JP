---
title: サービスのアダプターを Windows SharePoint の問題を診断する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 67aa43628e8db4384a411fd1cc4696b7955b3752
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249002"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="78e36-102">Windows SharePoint Services アダプターに関する問題を診断する方法</span><span class="sxs-lookup"><span data-stu-id="78e36-102">How to Diagnose Problems with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="78e36-103">このセクションでは、Windows Sharepoint Services アダプターに関する問題の診断に使用できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="78e36-103">This section contains steps that can be followed to help diagnose problems with the Windows Sharepoint Services adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="78e36-104">IIS サーバーの IIS ログ ファイルと TTPERR ログ ファイルでエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="78e36-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
-   <span data-ttu-id="78e36-105">ソースまたはターゲットの IIS サーバー ログ ファイルには、Windows Sharepoint Services アダプターに関する問題のトラブルシューティングに役立つ情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="78e36-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the Windows Sharepoint Services adapter.</span></span> <span data-ttu-id="78e36-106">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="78e36-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="78e36-107">*%Windir%\\*system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="78e36-107">*%WinDir%\\*system32\LogFiles\W3SVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78e36-108">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="78e36-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
-   <span data-ttu-id="78e36-109">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="78e36-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="78e36-110">*%Windir%\\*system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="78e36-110">*%WinDir%\\*system32\LogFiles\HTTPERR\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78e36-111">HTTPERR ログ ファイルは、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] コンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="78e36-111">The HTTPERR log file is only available on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e36-112">参照</span><span class="sxs-lookup"><span data-stu-id="78e36-112">See Also</span></span>  
 <span data-ttu-id="78e36-113">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="78e36-113">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="78e36-114">Windows SharePoint Services アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="78e36-114">Troubleshooting the Windows SharePoint Services Adapter</span></span>](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)