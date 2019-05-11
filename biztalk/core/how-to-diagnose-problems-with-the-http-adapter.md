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
ms.openlocfilehash: 1496ed936629a502d9274800455fd79334260f51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385250"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a><span data-ttu-id="fcf23-102">HTTP アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="fcf23-102">How to Diagnose Problems with the HTTP Adapter</span></span>
<span data-ttu-id="fcf23-103">このセクションには、HTTP アダプターに関する問題の診断に役立つことができますの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fcf23-103">This section contains steps that can be followed to help diagnose problems with the HTTP adapter.</span></span>  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a><span data-ttu-id="fcf23-104">IIS および HTTPERR ログ ファイルの IIS サーバーのエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcf23-104">Check the IIS and HTTPERR log files of the IIS Server for errors</span></span>  
  
- <span data-ttu-id="fcf23-105">ソースまたはターゲット IIS サーバーのログ ファイルは、HTTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fcf23-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the HTTP adapter.</span></span> <span data-ttu-id="fcf23-106">既定では、IIS は Windows Server 上のログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="fcf23-106">By default the IIS log files on a Windows Server are located in the following directory:</span></span>  
  
   <span data-ttu-id="fcf23-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="fcf23-107"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="fcf23-108">*%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="fcf23-108">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="fcf23-109">既定では、HTTPERR ログ ファイル、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]ベースのコンピューターは、次のディレクトリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="fcf23-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] based computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="fcf23-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="fcf23-110"><em>%WinDir%\\</em>system32\LogFiles\HTTPERR\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="fcf23-111">HTTPERR ログ ファイルは上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="fcf23-111">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a><span data-ttu-id="fcf23-112">System.Net.HttpWebRequest クラスを使用するクライアントで送信先 URL への投稿の HTTP 送信アダプターに関する問題を分離します。</span><span class="sxs-lookup"><span data-stu-id="fcf23-112">Isolate problems with the HTTP send adapter by posting to the destination URL with a client that uses the System.Net.HttpWebRequest class</span></span>  
  
1.  <span data-ttu-id="fcf23-113">HTTP 送信アダプターには、送信先 URL に投稿するときにエラーが生成している場合、は、送信先 URL に投稿する、System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="fcf23-113">If the HTTP send adapter is generating errors when posting to the destination URL, create a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes to post to the destination URL.</span></span> <span data-ttu-id="fcf23-114">このアプローチは、問題が、HTTP 送信アダプターに固有であるか、一般に、送信先 URL への問題の投稿がある場合かを確認に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fcf23-114">This approach will help determine if the problem is specific to the HTTP send adapter or if there is a problem posting to the destination URL in general.</span></span>  
  
2.  <span data-ttu-id="fcf23-115">詳細については、System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントを作成する方法を参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://go.microsoft.com/fwlink/?LinkId=66987)します。</span><span class="sxs-lookup"><span data-stu-id="fcf23-115">For more information about creating a client that uses the System.Net.HttpWebRequest and HttpWebResponse classes see [How to use the new System.Net classes to create an HTTP client](http://go.microsoft.com/fwlink/?LinkId=66987).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf23-116">参照</span><span class="sxs-lookup"><span data-stu-id="fcf23-116">See Also</span></span>  
 <span data-ttu-id="fcf23-117">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="fcf23-117">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="fcf23-118">HTTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fcf23-118">Troubleshooting the HTTP Adapter</span></span>](../core/troubleshooting-the-http-adapter.md)