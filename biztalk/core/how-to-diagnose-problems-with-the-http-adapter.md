---
title: HTTP アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110ae50f97d89b12b361a14caaac4f0df56989e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015723"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a><span data-ttu-id="42a6a-102">HTTP アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="42a6a-102">How to Diagnose Problems with the HTTP Adapter</span></span>
<span data-ttu-id="42a6a-103">ここでは HTTP アダプターに関する問題の診断手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="42a6a-103">This section contains steps that can be followed to help diagnose problems with the HTTP adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="42a6a-104">IIS サーバーの IIS ログ ファイルと TTPERR ログ ファイルでエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="42a6a-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="42a6a-105">ソースまたはターゲットの IIS サーバー ログ ファイルには、HTTP アダプターに関する問題のトラブルシューティングに役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="42a6a-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the HTTP adapter.</span></span> <span data-ttu-id="42a6a-106">既定では、Windows Server の IIS ログ ファイルは、次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="42a6a-106">By default the IIS log files on a Windows Server are located in the following directory:</span></span>  
  
   <span data-ttu-id="42a6a-107"><em>%Windir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="42a6a-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="42a6a-108">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="42a6a-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="42a6a-109">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="42a6a-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="42a6a-110"><em>%Windir%\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="42a6a-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="42a6a-111">HTTPERR ログ ファイルは上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="42a6a-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a><span data-ttu-id="42a6a-112">System.Net.HttpWebRequest クラスを使用するクライアントを送信先 URL に POST して、HTTP 送信アダプターの問題を切り分ける</span><span class="sxs-lookup"><span data-stu-id="42a6a-112">Isolate problems with the HTTP send adapter by posting to the destination URL with a client that uses the System.Net.HttpWebRequest class</span></span>  
  
1.  <span data-ttu-id="42a6a-113">送信先 URL への POST を実行したときに HTTP 送信アダプターでエラーが生成される場合は、System.Net.HttpWebRequest クラスと HttpWebResponse クラスを使用するクライアントを作成して送信先 URL に POST します。</span><span class="sxs-lookup"><span data-stu-id="42a6a-113">If the HTTP send adapter is generating errors when posting to the destination URL, create a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes to post to the destination URL.</span></span> <span data-ttu-id="42a6a-114">この方法は、問題が HTTP 送信アダプター限定のものであるか、送信先 URL への POST に関する一般的なものであるかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="42a6a-114">This approach will help determine if the problem is specific to the HTTP send adapter or if there is a problem posting to the destination URL in general.</span></span>  
  
2.  <span data-ttu-id="42a6a-115">詳細については、System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントを作成する方法を参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://go.microsoft.com/fwlink/?LinkId=66987)します。</span><span class="sxs-lookup"><span data-stu-id="42a6a-115">For more information about creating a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes see [How to use the new System.Net classes to create an HTTP client](http://go.microsoft.com/fwlink/?LinkId=66987).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a6a-116">参照</span><span class="sxs-lookup"><span data-stu-id="42a6a-116">See Also</span></span>  
 <span data-ttu-id="42a6a-117">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="42a6a-117">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="42a6a-118">HTTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="42a6a-118">Troubleshooting the HTTP Adapter</span></span>](../core/troubleshooting-the-http-adapter.md)