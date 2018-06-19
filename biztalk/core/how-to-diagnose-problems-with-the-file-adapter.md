---
title: ファイル アダプターに関する問題を診断する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f06089a5-4747-4879-a796-157088868dba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0481a3abdf497c093a87d7d74ea0356c7cad0d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249042"
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a><span data-ttu-id="6b646-102">ファイル アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="6b646-102">How to Diagnose Problems with the File Adapter</span></span>
<span data-ttu-id="6b646-103">ここでは、ファイル アダプターに関する問題の診断手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b646-103">This section contains steps that can be followed to help diagnose problems with the File adapter.</span></span>  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a><span data-ttu-id="6b646-104">ファイル受信アダプターまたはファイル送信アダプターを使用したときに発生するエラーを診断するため、FileMon ユーティリティを実行する</span><span class="sxs-lookup"><span data-stu-id="6b646-104">Run the FileMon Utility to diagnose errors that occur using the File Receive or File Send Adapter</span></span>  
  
1.  <span data-ttu-id="6b646-105">FileMon ユーティリティをダウンロード[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)です。</span><span class="sxs-lookup"><span data-stu-id="6b646-105">Download the FileMon utility from [www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235).</span></span>  
  
2.  <span data-ttu-id="6b646-106">ファイル アダプターの読み書き対象フォルダーまたは共有をホストするサーバー上に、Filemon ユーティリティをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b646-106">Install the Filemon utility on the server that hosts the folder or share that is being read from or written to by the File Adapter.</span></span>  
  
3.  <span data-ttu-id="6b646-107">Filemon ユーティリティを起動し、フィルターを適用して、ファイル アダプターのハンドラーが実行されている BizTalk ホスト インスタンス (BTSNTSvc.exe など) でのファイル アクセスのみを監視するようにします。</span><span class="sxs-lookup"><span data-stu-id="6b646-107">Launch the Filemon utility and apply a filter to monitor only file accesses that are being made by the BizTalk Host instance that the file adapter handlers are running in (for example BTSNTSvc.exe).</span></span>  
  
4.  <span data-ttu-id="6b646-108">問題を発生させるシナリオを再現します。</span><span class="sxs-lookup"><span data-stu-id="6b646-108">Run the scenario that caused the problem.</span></span>  
  
5.  <span data-ttu-id="6b646-109">Filemon ユーティリティのファイル監視を無効にし、生成されたログ ファイルをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="6b646-109">Disable file monitoring in the Filemon utility, then save the generated log file to disk.</span></span>  
  
6.  <span data-ttu-id="6b646-110">生成されたログ ファイルで、エラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b646-110">Review the generated log file for any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b646-111">Microsoft では FileMon をサポートしておらず、このプログラムの適合性に関して保証しません。</span><span class="sxs-lookup"><span data-stu-id="6b646-111">FileMon is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="6b646-112">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="6b646-112">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b646-113">参照</span><span class="sxs-lookup"><span data-stu-id="6b646-113">See Also</span></span>  
 <span data-ttu-id="6b646-114">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="6b646-114">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="6b646-115">ファイル アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6b646-115">Troubleshooting the File Adapter</span></span>](../core/troubleshooting-the-file-adapter.md)