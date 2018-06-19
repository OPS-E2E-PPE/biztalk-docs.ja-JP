---
title: HTTP アダプターに関する問題を診断する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 545e095624c30b4611c74dcfbdead13d685164ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249842"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a><span data-ttu-id="16375-102">HTTP アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="16375-102">How to Diagnose Problems with the HTTP Adapter</span></span>
<span data-ttu-id="16375-103">ここでは HTTP アダプターに関する問題の診断手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="16375-103">This section contains steps that can be followed to help diagnose problems with the HTTP adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="16375-104">IIS サーバーの IIS ログ ファイルと TTPERR ログ ファイルでエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="16375-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
-   <span data-ttu-id="16375-105">ソースまたはターゲットの IIS サーバー ログ ファイルには、HTTP アダプターに関する問題のトラブルシューティングに役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="16375-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the HTTP adapter.</span></span> <span data-ttu-id="16375-106">既定では、Windows Server の IIS ログ ファイルは、次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="16375-106">By default the IIS log files on a Windows Server are located in the following directory:</span></span>  
  
     <span data-ttu-id="16375-107">*%Windir%\\*system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="16375-107">*%WinDir%\\*system32\LogFiles\W3SVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="16375-108">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="16375-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
     <span data-ttu-id="16375-109">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="16375-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="16375-110">*%Windir%\\*system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="16375-110">*%WinDir%\\*system32\LogFiles\HTTPERR\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="16375-111">HTTPERR ログ ファイルが上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="16375-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a><span data-ttu-id="16375-112">System.Net.HttpWebRequest クラスを使用するクライアントを送信先 URL に POST して、HTTP 送信アダプターの問題を切り分ける</span><span class="sxs-lookup"><span data-stu-id="16375-112">Isolate problems with the HTTP send adapter by posting to the destination URL with a client that uses the System.Net.HttpWebRequest class</span></span>  
  
1.  <span data-ttu-id="16375-113">送信先 URL への POST を実行したときに HTTP 送信アダプターでエラーが生成される場合は、System.Net.HttpWebRequest クラスと HttpWebResponse クラスを使用するクライアントを作成して送信先 URL に POST します。</span><span class="sxs-lookup"><span data-stu-id="16375-113">If the HTTP send adapter is generating errors when posting to the destination URL, create a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes to post to the destination URL.</span></span> <span data-ttu-id="16375-114">この方法は、問題が HTTP 送信アダプター限定のものであるか、送信先 URL への POST に関する一般的なものであるかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16375-114">This approach will help determine if the problem is specific to the HTTP send adapter or if there is a problem posting to the destination URL in general.</span></span>  
  
2.  <span data-ttu-id="16375-115">System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントの作成の詳細については、次を参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://go.microsoft.com/fwlink/?LinkId=66987)です。</span><span class="sxs-lookup"><span data-stu-id="16375-115">For more information about creating a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes see [How to use the new System.Net classes to create an HTTP client](http://go.microsoft.com/fwlink/?LinkId=66987).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16375-116">参照</span><span class="sxs-lookup"><span data-stu-id="16375-116">See Also</span></span>  
 <span data-ttu-id="16375-117">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="16375-117">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="16375-118">HTTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="16375-118">Troubleshooting the HTTP Adapter</span></span>](../core/troubleshooting-the-http-adapter.md)